### Adpro Tutorial 8: Publisher
## How many data your publlsher program will send to the message broker in one run?
Based on main.rs, I believe it's 5. 

## The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
The same as the subscriber program. That is, amqp is the protocol, guest:guest is the username and password, and localhost:5672 is the host and port.

## Screenshot of running RabbitMQ 
![Running RabbitMQ](img/running-rabbitmq.png)

## Screenshot of cargo run publisher 
`cargo run` in the publisher directory, sending 5 messages to the message broker
![Cargo Run Publisher](img/cargo-run-publisher.png)
The subscriber got the message
![Cargo Run Subscriber](img/cargo-run-subscriber.png)

## Monitoring chart based on publisher 
![Monitoring RabbitMQ](img/monitoring-rabbitmq.png)
The spike in the chart corresponds to the message sent by the publisher. Each `cargo run` sends a message to the message broker. When I did `cargo run` twice, the spike in the chart is twice as high.