# dev_RabbitMQ
RabbitMQ Prototyping and Development

##### Basic Setup with Docker
- Create folder dev_RabbitMQ
- Create docker-compose.yml:
  ```
  version: "3.2"
  services:
    rabbitmq:
      image: rabbitmq:3-management-alpine
      container_name: 'rabbitmq'
      ports:
          - 5672:5672
          - 15672:15672
      volumes:
          - ~/.docker-conf/rabbitmq/data/:/var/lib/rabbitmq/
          - ~/.docker-conf/rabbitmq/log/:/var/log/rabbitmq
      networks:
          - rabbitmq_dev_net

    networks:
      rabbitmq_dev_net:
        driver: bridge
    ```
    
    - To Run:
    ```
    $cd dev_RabbitMQ
    $docker-compose up
    ```
    
    
    
##### Using with GO Client

##### Using with Python Pika Client
- Install pika
  ```
  $python -m pip install pika --upgrade
  ```
