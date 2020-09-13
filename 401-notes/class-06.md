## Redis FROM https://aws.amazon.com/redis/
- REDIS - REmote DIctionary Service (first release was in 2009 - now on version 5.x.x)
- Salvatore Sanfilippo - Original inventor 
- REDIS - popular choice for session management, caching, leader boards, chat/messaging, realtime, etc. 
  - REDIS data is stored in-memory (rather than on SSD or another disk like PostgreSQL, MongoDB, etc.)...is fast!
  - many options for data types (Strings, Lists, Sets, Bitmaps, etc)
  - simplicity (less lines of code to store)
  - replication and persistance (better read performance because requests can be split between servers). Persistance: Point-in-time backups of data.
  - scalability 
  - large community and is widely supported 
- REDIS vs Memcached 
- REDIS and language support (Python, Java, PHP, Perl, Go, Ruby, C/C#/C++, JavaScript, Node.js)

## What is a queue? FROM https://www.educative.io/edpresso/what-is-a-queue
- Similar to the stack, the query orders elements in a sequence. 
  - Uses first in, first out (FIFO) method...like people waiting in line. 
- Terms
  - `Enqueue()` - add a element to end of queue
  - `Dequeue()` - element is removed from start of queue 
  - `isEmpty()` - this returns 'true' if there is nothing in the queue (empty)
  - `Top()` - this returns the first element in the queue (the top of the queue)

## Task Queue Overview - 6.4 Task queues FROM https://redislabs.com/ebook/part-2-core-concepts/chapter-6-application-components-in-redis/6-4-task-queues/
- Multiple request from web clients, tasks are deferred and go into a queue to be processed later. 
- There are task queue softwares like ActiveMQ, RabbitMQ, Gearman, Amazon SQS, etc. 

## Task Queue - FIFO - 6.4.1 First-in, first-out queues FROM https://redislabs.com/ebook/part-2-core-concepts/chapter-6-application-components-in-redis/6-4-task-queues/6-4-1-first-in-first-out-queues/

- First in First out
- Last in First out
- Priority queues

- Definitions: 
  - Latency: The time is data to be transferred between source and destination (measured in milliseconds)
  - serialization: translating the data structure into a format that can be stored or transmitted and then changed back to original structure again later.

- `BLPOP` - first LIST with items will have one popped from the front --> `BRPOP` last one will have one popped.

- REDIS Email list example: (high latency)
  - task queue to keep track of who receives an email and why
  - worker process sends multiple emails at a time should the outgoing email servers become slow.
  - emails to send go in queue 
  - no duplications

- Executing multiple tasks 
- task priorities (send password reset emails before upcoming events email, completed sales before upcoming sales email, etc.)
  - Set priorities (high, medium, low)
    - multiple queues help with priority implementation.
    - sometimes queues need to be reordered to be more "fair" to the other queues, like if one is growing more quickly. 

## Bull FROM https://optimalbits.github.io/bull/

- Bull (node library): implements a fast queue based on REDIS. 
- Needs to be installed `npm install bull --save`. Need to have REDIS server running to use Bull. Bull tries to connect to `localhost:6379` by default. 
- Create a new instance of Bull `const myFirstQueue = new Bull('my-first-queue');`
- Queues (3 main roles) 
  - job producer: can add jobs to the queue regardless if there are consumers
  - job consumer/worker (processes)
  - events listener
- Queues have asynchronous communication 
- More than one worker can be working on jobs in queue using either FIFO/LIFO/Priorities. 

- Bull Lifecycle 
  - Job added by producer and it is either in "wait" or "delay" status (there is a timeout or it needs to be promoted to be processed).
  - Jobs go to an "active" state which are jobs that are being processed at the moment. This ends with either "completed" or "failed". 

- Stalled Jobs - a job where the process function takes too long and worker is unsure if queue is still working on the job. It can be processed by another idle worker or moved to "failed" status. 
- Events: add the word `global` to listen to all events. 

- Queue options:
  - Rate limiter - limit the amount of jobs processed in a specific amount of time. 
  - Named jobs - can give jobs names. This does not have an operational impact.
  - "Sandboxed" processes (concurrency setting)- workers can process several jobs at the same time. 

- Job Types:
  - Bull is FIFO by default
  - Can have LIFO - `const myJob = await myqueue.add({ foo: 'bar' }, { lifo: true });` (EXAMPLE FROM SITE)
  - Can delay the time before a job is processed by adding `{ delay: 5000 }` for a delay of 5 seconds. 
  - Prioritize: Can add `{ priority: 3 }` to indicate a job is of low priority. NOTE: Priority queues are a little slower AND High priority is 1. 
  - Repeatable - cron jobs - NOTE(S): Bull will not add the same repeatable job. Jobs will not accumulate if a worker is not online. Jobs can be removed using `removeRepeatable` (method). 