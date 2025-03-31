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
