Split-Brain问题说的是1个集群如果发生了网络故障，很可能出现1个集群分成了两部分，而这两个部分都不知道对方是否存活，不知道到底是网络问题还是直接机器down了，所以这两部分都要选举1个Leader，而一旦两部分都选出了Leader, 并且网络又恢复了，那么就会出现两个Brain的情况，整个集群的行为不一致了。

1. Quorums: 即只有集群中超过半数节点投票才能选举出Leader。
2. Redundant communications: 冗余通信的方式，集群中采用多种通信方式，防止一种通信方式失效导致集群中的节点无法通信。
3. Fencing: 共享资源的方式，比如能看到共享资源就表示在集群中，能够获得共享资源的锁的就是Leader，看不到共享资源的，就不在集群中

还有权值

