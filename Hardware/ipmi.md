### remote terminal
`ipmitool -I lanplus -H 192.168.X.X -U USERNAME -P PASSWORD sol activate`

### Server ACPI shutdown

`ipmitool -I lanplus -H 192.168.X.X -U USERNAME -P PASSWORD power soft`


###

`ipmitool -I open <command>`
以下為IOL下的指令：
###

`ipmitool -I <lanplus> -H <hostname> [-U <username>] [-P <password>] <command>`
基本參考：http://starbots.org/cgi-bin/man/man2html?ipmitool+1
 
###

`ipmitool sel info：看一些information`
###

`ipmitool sel list ：get a list sel records`
###

`ipmitool sel elist ：get detial sel`
###

`ipmitool sel time get ：check BMC clock`
###

`ipmitool sel time set ：setting BMC clock`
###

`ipmitool sel clear ：將information清除`
 
###

`ipmitool mc info：BMC H/W 相關訊息`
###

`ipmitool mc reset cold ：BMC reset`
###

`ipmitool mc selftest ：`
###

`ipmitool mc getenables ：列出所有BMC允許的選項`
###

`ipmitool mc setenables ：`
 
###

`ipmitool –I open event 1：發送一個溫度過高的訊號到System Event Log中`
1 Temperature：Upper Critical going high
2 Voltage threshold：Lower Crirical going low
3 Memory：Correctable ECC error detected
###

`ipmitool -I open event ：測試配置的IPMI中的snmp功能是否成功`
 
Change ipmi addr
###

`ipmitool lan set 1 ipaddr 192.168.1.200：將lan1 ip 設成192.168.1.200，執行這個指令的時候網路線要記得拔起來`
###

`ipmitool lan set 1 ipsrc dhcp ：DHCP`
###

`ipmitool lan print ：可以檢查ip是否已經被更改了`
###

`ipmitool -I open lan set 1 snmp public設置channel 1 上snmp的community為public`
###

`ipmitool -I open lan set 1 access on設置channel 1允許訪問`
 
###

`ipmitool sel time get：check BMC的時間`
###

`ipmitool sel time set “mm/dd/yyyy hh:mm:ss”`
 
###

`ipmitool power status 查看目前的電源狀況`
###

`ipmitool power on 開機`
###

`ipmitool power off 關機，是暴力關電，所以OS不是正常結束`
###

`ipmitool power reset如同按下reset`
###

`ipmitool power cycle 似乎是讓系統先shutdown之後，過一秒再power on，這樣就不必常跑機房了`
###

`ipmitool power soft 透過ACPI讓OS shutdown或restart或log off`
 
###

`ipmitool chassis status ：system status包含電源訊息，system狀況`
###

`ipmitool chassis identify ：可以在機房機架中找到主機，燈號會閃15秒`
###

`ipmitool chassis restart_cause ：查看上次系統重啟的原因`
###

`ipmitool –I open chassis policy list 查看電源相關策略`
###

`ipmitool chassis poh ：`
###

`ipmitool chassis selftest ：`