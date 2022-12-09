# XDP DROP

1- Install the following packages.
bash```
sudo apt install clang llvm libelf-dev libpcap-dev gcc-multilib build-essential
```

2- Build and dump the BPF object.
bash```
clang -O2 -g -Wall -target bpf -c xdp_drop.c -o xdp_drop.o
```

3- Load a BPF object.
bash```
sudo ip link set veth1 xdpgeneric obj xdp_drop.o sec xdp_drop
```
