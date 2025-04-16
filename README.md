# FIWARE-System-Deployment
-- iot agent
root@ubuntu-s-2vcpu-4gb-amd-fra1-01:~# curl http://localhost:4061/iot/about
{"libVersion":"4.7.0-next","port":"4061","baseRoot":"/","version":"3.7.0-next"}root@ubuntu-s-2vcpu-4gb-amd-fra1-01:~# ^C
--broker
root@ubuntu-s-2vcpu-4gb-amd-fra1-01:~# curl -X GET "http://localhost:1026/version"
{
"orion" : {
  "version" : "4.1.0",
  "uptime" : "0 d, 0 h, 13 m, 10 s",
  "git_hash" : "95d82a97d3d1128b42c79e5c2f659a0d19a0687f",
  "compile_time" : "Thu Sep 12 12:02:08 UTC 2024",
  "compiled_by" : "root",
  "compiled_in" : "buildkitsandbox",
  "release_date" : "Thu Sep 12 12:02:08 UTC 2024",
  "machine" : "x86_64",
  "doc" : "https://fiware-orion.rtfd.io/en/4.1.0/"
}
}
root@ubuntu-s-2vcpu-4gb-amd-fra1-01:~# cat device_registration.json 
{
  "devices": [
    {
      "device_id": "device-002",
      "device_name": "esp32",
      "entity_name": "device-002",
      "entity_type": "TemperatureSensor",
      "protocol": "MQTT",
      "protocol_version": "v1",
      "attributes": [
        {
          "object_id": "temperature",
          "name": "temperature",
          "type": "float"
        },
        {
          "object_id": "humidity",
          "name": "humidity",
          "type": "float"
        },
        {
          "object_id": "flame",
          "name": "flame",
          "type": "int"
        },
        {
          "object_id": "sound",
          "name": "sound",
          "type": "int"
        },
        {
          "object_id": "battery",
          "name": "battery",
          "type": "float"
        }
      ],
      "apiKey": "987654321k"
    }
  ]
}
root@ubuntu-s-2vcpu-4gb-amd-fra1-01:~#  curl -X POST   -H "Content-Type: application/json"   -H "Fiware-Service: howtoService"   -H "Fiware-ServicePath: /howto"   -d @device_registration.json   http://localhost:4061/iot/devices

root@ubuntu-s-2vcpu-4gb-amd-fra1-01:~# curl -X GET   http://localhost:4061/iot/devices   -H "Fiware-Service: howtoService"   -H "Fiware-ServicePath: /howto"
{"count":1,"devices":[{"device_id":"device-002","service":"howtoservice","service_path":"/howto","entity_name":"device-002","entity_type":"TemperatureSensor","transport":"MQTT","attributes":[{"object_id":"temperature","name":"temperature","type":"float"},{"object_id":"humidity","name":"humidity","type":"float"},{"object_id":"flame","name":"flame","type":"int"},{"object_id":"sound","name":"sound","type":"int"},{"object_id":"battery","name":"battery","type":"float"}],"lazy":[],"commands":[],"static_attributes":[],"protocol":"MQTT"}]}root@ubuntu-s-2vcpu-4gb-amd-fra1-01:~# 








