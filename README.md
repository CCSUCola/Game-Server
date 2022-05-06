# Game-Server
编译代码

GateServer编译： g++ GateServer.cpp MsgQueue.cpp CEpoll.cpp project.pb.cc -lprotobuf -o GateServer -std=c++11 -lpthread -I/usr/include/mysql/ -L/usr/lib64/mysql -L/usr/local/lib/ -lmysqlclient -L/usr/local/lib/ -lhiredis

GameServer编译： g++ GameServer.cpp MsgQueue.cpp CSql.cpp CRedis.cpp project.pb.cc -lprotobuf -o GameServer -std=c++11 -lpthread -I/usr/include/mysql/ -L/usr/lib64/mysql -L/usr/local/lib/ -lmysqlclient -L/usr/local/lib/ -lhiredis

DBServer编译： g++ DBServer.cpp MsgQueue.cpp CSql.cpp BitMap.cpp CRedis.cpp project.pb.cc -lprotobuf -o DBServer -std=c++11 -lpthread -I/usr/include/mysql/ -L/usr/lib64/mysql -L/usr/local/lib/ -lmysqlclient -L/usr/local/lib/ -lhiredis

protobuf生成.cc和.h文件：  protoc --cpp_out=./ project.proto

进程运行顺序：GateServer DBServer GameServer
