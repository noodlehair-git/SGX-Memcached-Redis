# Introduction 

Many cloud service providers have adopted key-value caches such as Redis and Memcached in order to improve throughput and reduce latency for their service. However, data security is still a major concern, which affects the adoption of cloud caches. This is mainly because of the multi-tenant cloud environment which faces threats from both co-located other tenants, as well as the untrusted cloud provider.
One way of providing data confidentiality and privacy is by leveraging Intel Software Guard Extensions (SGX). The aim of this project is to run Redis inside an enclave using the Graphene-SGX and study its implications. Experimental results show that EnclaveCache achieves comparable performance to traditional key-value chaches.

# Tools and setup

1. Set up the [linux-sgx-driver](https://github.com/intel/linux-sgx-driver) and [linux-sdk](https://github.com/intel/linux-sgx).

2. Install [Graphene-SGX](https://github.com/oscarlab/graphene).

3. Install [memtier_benchmark](https://github.com/RedisLabs/memtier_benchmark).

# Experimentation

The experimentation has been done on Intel NUC (NUC10i7FNH) on HW mode which runs Ubuntu 18.04 OS. To perform the experimentation follow the steps below. 

To run in SGX HW mode

```cd graphene/Examples/redis```

```make SGX=1```

```SGX=1 ./pal_loader redis-server --save '' --protected-mode no & memtier_benchmark -c 70 --hide-histogram```



To run in SGX SIM mode

```./pal_loader redis-server --save '' --protected-mode no & memtier_benchmark -c 70 --hide-histogram```



To simply run Redis

```make clean```

```./redis-server --save '' --protected-mode no & memtier_benchmark -c 70 --hide-histogram```

Learn more about memtier_benchmark usage from [here](https://redislabs.com/blog/memtier_benchmark-a-high-throughput-benchmarking-tool-for-redis-memcached/).


# Result

# Conclusion

# References

1. Chen, Lixia, et al. "EnclaveCache: A Secure and Scalable Key-value Cache in Multi-tenant Clouds using Intel SGX." Proceedings of the 20th International Middleware Conference. 2019.
