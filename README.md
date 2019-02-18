# RabbitMq
Rabbit Mq Demo with Spring boot

RabbitMq:
	Messaging provides a way to communicate loosely, asynchronously, and progressively. There are many protocols that exist that 
	provide this feature, and AMQP is one of the most popular and robust.
	
	AMQP (Advanced Message Queuing Protocol) is a protocol that RabbitMQ uses for messaging. 
	
	RabbitMQ is a powerful, open-source message broker. 
	
	Steps for Setup :
		Install Erlang : http://www.erlang.org/downloads
		Install RabbitMq : https://www.rabbitmq.com/install-windows.html
		
		Guide : https://www.rabbitmq.com/install-windows-manual.html
		
		set environment variables
		
		rabbitmq-plugins enable rabbitmq_management - for setting up the management pkugins.
		
		rabbitmqctl add_user test test -For creating a new user if necessary
		
		rabbitmq-service.bat install start stop...
		
		rabbitmqctl.bat start_app
	
	Terms :
	
	Exchange - Takes a message and routes it to one or more queues. Routing algorithms decides where to send the message from the exchange.
	Routing algorithms depends on the exchange type and rules called “bindings.”
	
	Exchange Types:
		Direct-It routes messages with a routing key equal to the routing key declared by the binding queue
		Fanout-It routes messages to all the queues from the bound exchange. If routing key is provided then it will be ignored
		Topic-It routes messages to queues based on either full or a portion of routing key matches
		Headers-Routes messages based upon matching of the message header to specified header based on binding queue
		
	Topics: Topics are the subject part of the messages. These are the optional parameters for message exchange.
	
	Bindings: "Bindings" is the glue that holds exchanges and queues together. These are the rules for routing algorithms.
	
	Queue: Queue is a container for messages. It is only bound by the host’s memory and disk limit. Queues are the final destination 
	for messages before being popped up by subscribers.
	
	Producer: Producer is a program that sends message to a queue.

	Consumer: A consumer is a program which receives messages from the queue.
	
	
	Program :
		UserService : The Class that contains the controller
		MessageSender : The Class that sends the message to the queue
		MessageListener : The Class which is notified when there is a message in the queue
	
