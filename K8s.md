* 如果想像整個 cluster 是一個船隊，那麼 Node 就是船、Pod 就是船上的貨櫃，容器就是貨櫃裡的貨物、貨物由 Container Runtime 產生。

* 所有的船 (Node) 都有這三個組件：kubelet、kube-proxy、Container Runtime。
  
* 在船隊中擔任總指揮的主船 (Master Node)，則另外擁有這四個元件 : kube-apiserver、etcd、kube-scheduler、kube-controller-manager。

* 總指揮(Master Node)的傳達給小船(Worker Node)的各種指令，都是由 kube-apiserver 發送給船長 kubelet 來完成的。

* 船上的通訊系統由 CNI 負責發 IP、kube-proxy 負責轉發流量。