# AWS-SQS

SQS message queue:

why SQS? transferring data's interms of message and events.

Publisher -> Queue -> consumer

publisher publish the message to queue first in first out and consumer will continuously polling the queue and get the message from consumer

Once message red by consumer, message will get deleted

Why SQS over api calls?
service 1 -> service 2 => if service 2 down means service 1 also getting down

SQS 
service 1 -> Queue -> service 2 => if service 2 is down means even service 1 will survive 

it is decoule service dependencies

common patterns in SQS
Fanout ->  one producer and multiple / many consumers
ex: 1 orderservice -> n of services like analytics queue, dashboard services queue
check screenshot 2 : 

from producer present in one aws infrastructure and receiver in one infrastructure

In producer side aws SNS topic is coupled with SQS and messages to produce to many consumers 

serverless processing with processing control -> SQS -> AWS lambda 

job buffering -> Cloud watch event queue -> SQS queue -> AWS EC2 or lambda  

important of SQS queue
many threads/ processes can poll a queue at once 
only a single thread / process can process a message at once 
long polling supported and encoraged
256kb is max message size

