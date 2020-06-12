# Introduction 

Many cloud service providers have adopted key-value caches such as Redis and Memcached in order to improve throughput and reduce latency for their service. However, data security is still a major concern, which affects the adoption of cloud caches. This is mainly because of the multi-tenant cloud environment which faces threats from both co-located other tenants, as well as the untrusted cloud provider.
One way of providing data confidentiality and privacy is by leveraging Intel Software Guard Extensions (SGX). The aim of this project is to run Redis inside an enclave using the Graphene-SGX and study its implications. Experimental results show that EnclaveCache achieves comparable performance to traditional key-value chaches.

# Tools and setup


# Experimentation

# Result

# Conclusion

# References

1. Chen, Lixia, et al. "EnclaveCache: A Secure and Scalable Key-value Cache in Multi-tenant Clouds using Intel SGX." Proceedings of the 20th International Middleware Conference. 2019.
