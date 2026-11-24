# lab1

# PARTE A

# PERGUNTA A.1:
  mininet> net
  h1 h1-eth0:s1-eth1
  h2 h2-eth0:s1-eth2
  h3 h3-eth0:s1-eth3
  s1 lo:  s1-eth1:h1-eth0 s1-eth2:h2-eth0 s1-eth3:h3-eth0
  c0
  mininet>

# PERGUNTA A.2:
  mininet> sh ovs-ofctl dump-flows s1
  mininet> h1 ping -c 3 h2
  PING 10.0.0.2 (10.0.0.2) 56(84) bytes of data.
  64 bytes from 10.0.0.2: icmp_seq=1 ttl=64 time=4.23 ms
  64 bytes from 10.0.0.2: icmp_seq=2 ttl=64 time=0.196 ms
  64 bytes from 10.0.0.2: icmp_seq=3 ttl=64 time=0.053 ms
  
  --- 10.0.0.2 ping statistics ---
  3 packets transmitted, 3 received, 0% packet loss, time 2016ms
  rtt min/avg/max/mdev = 0.053/1.494/4.234/1.938 ms
  mininet> sh ovs-ofctl dump-flows s1
   cookie=0x0, duration=3.551s, table=0, n_packets=0, n_bytes=0, idle_timeout=60, priority=65535,arp,in_port="s1-eth2",vlan_tci=0x0000,dl_src=00:00:00:00:00:02,dl_dst=00:00:00:00:00:01,arp_spa=10.0.0.2,arp_tpa=10.0.0.1,arp_op=2 actions=output:"s1-eth1"
   cookie=0x0, duration=3.551s, table=0, n_packets=2, n_bytes=196, idle_timeout=60, priority=65535,icmp,in_port="s1-eth1",vlan_tci=0x0000,dl_src=00:00:00:00:00:01,dl_dst=00:00:00:00:00:02,nw_src=10.0.0.1,nw_dst=10.0.0.2,nw_tos=0,icmp_type=8,icmp_code=0 actions=output:"s1-eth2"
   cookie=0x0, duration=3.549s, table=0, n_packets=2, n_bytes=196, idle_timeout=60, priority=65535,icmp,in_port="s1-eth2",vlan_tci=0x0000,dl_src=00:00:00:00:00:02,dl_dst=00:00:00:00:00:01,nw_src=10.0.0.2,nw_dst=10.0.0.1,nw_tos=0,icmp_type=0,icmp_code=0 actions=output:"s1-eth1"
  mininet>

# PERGUNTA A.3
  # (falta desenvolver essa resposta, mas é basicamente por ainda não termos aplicado nenhum limitador ou algo do género)

# PERGUNTA A.4
  # (falta desenvolver essa resposta, mas 66% dos pacotes são droppados)

