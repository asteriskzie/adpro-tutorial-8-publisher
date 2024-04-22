### Adpro Tutorial 8: Publisher
## How many data your publlsher program will send to the message broker in one run?
Based on the main.rs, I believe it's 5. In the main function, you can see 5 times an event is published. The event sends user ids and usernames. The usernames in order are Amir, Budi, Cica, Dira, and Emir. Each of these usernames represents a distinct message that is being sent to the mesage broker. Therefore the publisher program will send 5 messages to the message broker in one run. 

## The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
The URL is the same as in the subscriber program. It means that both the publisher and the subscriber are connecting to the same RabbitMQ server. It must be the same server for the functioning of our program. The publisher sends messages to the message broker. On the other hand, the subscriber receives messages from the message broker. Therefore, the publisher and the subscriber must connect to the same message broker. 

## Screenshot of running RabbitMQ 
![Running RabbitMQ](img/running-rabbitmq.png)

## Screenshot of cargo run publisher 
`cargo run` in the publisher directory. It sends 5 messages to the message broker:
![Cargo Run Publisher](img/cargo-run-publisher.png)
The subscriber got the messages:
![Cargo Run Subscriber](img/cargo-run-subscriber.png)
The messages are correctly received. They are the same as what we defined previously in the publisher program. We have successfully sent and received messages using RabbitMQ. 

## Monitoring chart based on publisher 
![Monitoring RabbitMQ](img/monitoring-rabbitmq.png)
The spike in the chart corresponds to the message sent by the publisher. Each `cargo run` sends a message to the message broker. The chart shows the message rates. The first spike is when I did `cargo run` once. It's peak is at 1.0/s, which means 1 message per second. When I did `cargo run` twice, the spike in the chart is twice as high. The peak is at 2.0/s, which means 2 messages per second. 