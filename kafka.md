1. Kafka là gì ? 
- Kafka là một stream plalform ( stream dữ liệu phân tán ) cung cấp khả năng publish là subcribe
- Kafka có thể đảm nhiệm công việc giao tiếp giữa các service, là nơi trung gian giao tiếp, giảm bớt sự phụ thuộc của các service với nhau 

2. Cấu trúc của Apache kafka 
- Producer : Một producer có thể là bất kì ứng dụng nào có chức năng publish message vào một topic
- Consumer : Một consumer có thể là bất kì ứng dụng nào có chức năng subcribe vào một topic và tiêu thụ tin nhắn 
- Topic    : Một topic là một category hoặc feed name nới mà record được publish  
- Message  : Message đơn thuần là một byte array và developer có thể dử dụng chúng để lưu bất cứ object với bất kỳ format nào - thông thường là String, Json và Avro
- Partitions : Các topic được chia nhỏ vào các đoạn khác nhau, các đoạn này được gọi là partition 
- Broker : Kafka cluster là một set các server, mỗi một set này được gọi là 1 broker, broker được coi là một node trong một cụm kafka, lưu trữ dữ liệu của một hoặc nhiều topic, mỗi partition được lưu trữ chính trên một broker (leader) và có các bản sao ( replica ) nằm trên các broker khác đảm bảo dữ liệu không bị mất khi một broker bị hỏng (follower)

- Zookeeper : Được dùng để quản lý và bố trí các broker 
* Vai trò của Zookeeper quản lý metadata, thông tin broker 

/kafka
  ├── /brokers
  │     ├── /ids/1  (Broker 1)
  │     ├── /ids/2  (Broker 2)
  │     ├── /ids/3  (Broker 3)
  │
  ├── /topics
  │     ├── /test-topic
  │          ├── /partitions
  │          │     ├── /0 (Leader: Broker 1)
  │          │     ├── /1 (Leader: Broker 2)
  │          │     ├── /2 (Leader: Broker 3)
  ├──────────────────────────────────────────


  * Một message được commit theo 2 cách 
    . Tự động : message sẽ tự động được đánh dấu hoàn thành sau một khoảng thời gian nhất định
    . Thủ công : consumer sau khi nhận được tin nhắn, thực hiện commit bằng cách gọi ack.commit 


  * Cách cài đặt kafka thủ công 
  B1 : cài đặt Java 
  B2 : Tải kafka từ trang chủ ( từ phiên bản 3.5 trở đi, kafka loại bỏ zookeeper mà thay vào đó là kraf dùng để quản lý)
  B3 : Cấu hình kafka ( server.properties ) và zookeeper ( zookeeper.properties) 
  B4 : Run zookeeper lên trước bằng câu lệnh :  
    bin\windows\zookeeper-server-start.bat config\zookeeper.properties
  B5 : Run kafka bằng câu lệnh 
    bin\windows\kafka-server-start.bat config\server.properties
  B6 : Tạo toptic mới : 
    bin\windows\kafka-topic.bat --create --topic <tên topic> --bootstrap-server <host:port> --replication-factor 1 --partitions 3 
  B7 : Liệt kê các topic : 
    bin\windows\kafka-topics.bat --list --bootstrap-server <host:port> 
  B8 : Chạy producer để gửi tin nhắn 
    bin\windows\kafka-console-producer.bat --broker-list <host:port> --topic <tên topic>
  B9 : Chạy consumer để nhận tin nhắn 
    bin\windows\kafka-console-consumer.bat --bootstrap-server <host:port> --topic <tên topic> --from-begining