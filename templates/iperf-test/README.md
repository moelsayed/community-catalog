simple stack used to test network performance on Rancher


It contains the following service:
  * iperfserver: iperf3 running in server mode. This only runs on hosts with lable "iperf_server=true"
  * iperfclient: iperf3 running in client mode. This picks a random iperf server and runs a test aginst it every 60 seconds and sends results to the logger service. It runs on hosts _without_ the "iperf_server=true" lable.
  * logger: simple flask app to log test results. Access logs using http://logger-service/static/containers.log
  * pilot: ubuntu container just in case to need it.
