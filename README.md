# kubeplugins
Bash скрипт scripts/kubectl-rusage призначений для виводу використання ресурсів в kubernetes кластері.

Для використання плагіну треба:

1.  Виставити файлу плагіну права на виконання 

   ```bash
   sudo chmod +x ./kubectl-rusage
   ```

2.  Помістити його, наприклад в /usr/local/bin 

   ```bash
   sudo cp ./kubectl-rusage /usr/local/bin 
   ```

Приклади використання:

1. Показати інформацію для nodes 

   ```bash
   kubectl rusage node
   ```

   Приклад виводу:

   ```bash
   |Resource  |Namespace      |Name                                                        |Cpu |Memory
   |node      |               |k3d-argo.cluster-agent-0                                    |30m |200Mi
   |node      |               |k3d-argo.cluster-agent-1                                    |18m |204Mi
   |node      |               |k3d-argo.cluster-server-0                                   |48m |586Mi
   ```

   

2. Показати інформацію для всіх подів 

   ```bash
   kubectl rusage pod
   ```

   Приклад виводу:

   ```bash
   |Resource  |Namespace      |Name                                                        |Cpu |Memory
   |pod       |argocd         |argocd-application-controller-0                             |11m |91Mi
   |pod       |argocd         |argocd-applicationset-controller-6f9d6cfd58-5mcnj           |1m  |28Mi
   |pod       |argocd         |argocd-dex-server-6df5d4f8c4-v45bp                          |1m  |24Mi
   |pod       |argocd         |argocd-notifications-controller-589b479947-dtdzh            |1m  |26Mi
   |pod       |argocd         |argocd-redis-b5d6bf5f5-x8x4r                                |1m  |8Mi
   |pod       |argocd         |argocd-repo-server-7b75b45897-svh5d                         |1m  |40Mi
   |pod       |argocd         |argocd-server-7459448d56-6jldh                              |1m  |32Mi
   |pod       |demo           |ambassador-5f859c79c9-fh8sh                                 |7m  |150Mi
   |pod       |demo           |cache-858575fc54-29p8h                                      |1m  |11Mi
   |pod       |demo           |db-7968646c85-5vqhm                                         |3m  |460Mi
   |pod       |demo           |demo-api-5479bcf989-dzflb                                   |1m  |18Mi
   |pod       |demo           |demo-ascii-548b45d685-7xskm                                 |1m  |19Mi
   |pod       |demo           |demo-data-78b5b48794-kmnmg                                  |1m  |18Mi
   |pod       |demo           |demo-front-548899b579-wr6gz                                 |1m  |15Mi
   |pod       |demo           |demo-img-5fd4bdf8bd-hcrs6                                   |1m  |17Mi
   |pod       |demo           |demo-nats-0                                                 |1m  |43Mi
   |pod       |demo           |demo-nats-box-f9c9b584c-hjpp5                               |1m  |0Mi
   |pod       |kube-system    |coredns-77ccd57875-c6grh                                    |2m  |27Mi
   |pod       |kube-system    |local-path-provisioner-957fdf8bc-jzqpl                      |1m  |18Mi
   |pod       |kube-system    |metrics-server-648b5df564-79pdt                             |3m  |37Mi
   |pod       |kube-system    |svclb-traefik-6eba338d-pnv5v                                |0m  |2Mi 
   |pod       |kube-system    |svclb-traefik-6eba338d-qc876                                |0m  |1Mi
   |pod       |kube-system    |svclb-traefik-6eba338d-sn5nm                                |0m  |1Mi
   |pod       |kube-system    |traefik-64f55bb67d-vrk78                                    |1m  |46Mi
   ```

   

3. Показати інформацію для поди в конкретному неймспейсі 

   ```bash
   kubectl rusage pod <namespace_name>
   ```

   Приклад виводу:

   ```bash
   |Resource  |Namespace      |Name                                                        |Cpu |Memory
   |pod       |demo           |ambassador-5f859c79c9-fh8sh                                 |7m  |150Mi
   |pod       |demo           |cache-858575fc54-29p8h                                      |1m  |10Mi
   |pod       |demo           |db-7968646c85-5vqhm                                         |3m  |460Mi
   |pod       |demo           |demo-api-5479bcf989-dzflb                                   |1m  |18Mi
   |pod       |demo           |demo-ascii-548b45d685-7xskm                                 |1m  |19Mi
   |pod       |demo           |demo-data-78b5b48794-kmnmg                                  |1m  |17Mi
   |pod       |demo           |demo-front-548899b579-wr6gz                                 |1m  |15Mi
   |pod       |demo           |demo-img-5fd4bdf8bd-hcrs6                                   |1m  |17Mi
   |pod       |demo           |demo-nats-0                                                 |1m  |43Mi
   |pod       |demo           |demo-nats-box-f9c9b584c-hjpp5                               |1m  |0Mi
   ```

   

