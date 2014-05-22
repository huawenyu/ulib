# ulib

An algorithm library for C (fork from http://code.google.com/p/ulib/)

# Target

The goal of this project is to provide extremely efficient
 implementations of some fundamental data structures and
 algorithms. The interface of each component has been made general and
 self-explanatory, one can grasp the usage by looking at the header of
 the component. I've implemented most of the components and the rest
 were ported from other open-source projects, such as the Linux
 kernel, of which all credits go the original authors.

    Main Features
        An extremely efficient open addressing hash table, comparable
        or even better performance than STL hashmap, Google
        sparse/dense hash, EASTL hashmap and RDESTL hashmap.
        A chaining hash table, corner stone for building concurrent
        hash tables.
        A concurrent hash table based on the chaining hash
        table. Significantly faster (~30%) than several popular ones,
        e.g., TBB(http://threadingbuildingblocks.org),
        nbds(http://code.google.com/p/nbds/) and Visual Studio
        2012. LocksCanMakeSense provides some analysis.
        The fast-hash hash function
        http://fast-hash.googlecode.com. Efficient and robust general
        purpose hash function.
        A set of robust, efficient, and invertible integer hash
        functions.
        Heap and heapsort. Improved performance than STL.
        A text binary search algorithm.
        A robust O(n) median algorithm.
        Various random number generators, e.g. Zipf RNG, Normal RNG,
        and Gamma RNG.
        General AVL and Splay trees. Faster than Solaris Kernel AVL
        and libavl.
        Bit tricks.
        Cryptographic algorithms. 

    Parallel Programming
        MapReduce framework for multicores.
        A set of scalable locks.
        Atomic primitives for x86_64. 

    Update History
        08/01/2013
            Added a patch to the SVN trunk. This patch fixes a
        segmentation fault raised in the sort() method of
        hash_chain. This issue only occurs when it is complied by
        certain buggy GCCs. If you have the hash_chain tests failed
        due to segmentation fault, please consider applying this
        patch. 
        Start from the version 2.0.0 beta, the ulib library targets
        only x86_64 architecture. In other words, newer versions may
        not compile/work on other architectures. 

    Performance
        Test codes can be located under perf/. 
        Hash table performance AlignedHashingPerformance.
        AVL tree performance AVLPerformance.
        Analysis of FastHash http://code.google.com/p/fast-hash/. 

    Core Items
        bfilter.{h,c}: the Bloom filter
        bitmap.{h,c}: generic bitmap
        crypt_aes.{h,c}: the AES crypt
        crypt_md5.{h,c}: the MD5 algorithm
        crypt_rc4.{h,c}: the RC4 crypt
        crypt_sha1.{h,c}: the SHA1 algorithm
        crypt_sha256.{h,c}: the SHA256 algorithm
        hash_open.h: C++ containers for the open addressing hashmap
        and hashset
        hash_open_prot.h: prototypes for the open addressing hashmap
        and hashset
        hash_chain.h: C++ container for the chain hashmap
        hash_chain_prot.h: prototype for the chain hashmap
        hash_func.{h,c}: hash functions
        heap_prot.h: generic heap prototype
        list.h: doubly linked list, can be used to implement queue and
        stack
        math_bit.h: bit operations
        math_bn.{h,c}: big number arithmetics
        math_comb.{h,c}: combinatorics enumerator
        math_factorial.{h,c}: factorial approximations
        math_gcd.{h,c}: Euclidean and the Extended Euclidean GCD
        algorithms
        math_lcm.{h,c}: the least common multiple
        math_rand_prot.h: pseudo-random number generators, mix
        functions, and etc
        math_rng_gamma.{h,c}: gamma distribution RNG
        math_rng_normal.{h,c}: normal distribution RNG
        math_rng_zipf.{h,c}: Zipf distribution RNG
        search_line.{h,c}: binary search for the text lines
        sort_heap_prot.h: prototype for the heapsort
        sort_list.{h,c}: list sort
        sort_median_prot.h: prototype for the median algorithm
        str_util.{h,c}: parallel/supplementary string utilities
        tree.{h,c}: various binary search trees
        tree_util.{h,c}: tree utilities
        ulib_ver.{h,c}: ulib version
        util_algo.h: basic algorithms
        util_console.{h,c}: command-line parser
        util_hexdump: the hexdump utilities
        util_log.h: logging utilities
        util_timer.h: high-precision timer 

    Parallel Items
        hash_chain_r.h: concurrent chain hashmap
        hash_multi_r.h: concurrent multiple hashmap
        mr_dataset.{h,cpp}: the MapReduce data abstraction
        mr_engine.h: the MapReduce engine
        mr_interm.h: the MapReduce intermediate storage abstraction
        os_atomic_intel64.h: atomic operations for the x86_64
        os_rdtsc.h: the Intel rdtsc instruction
        os_regionlock.h: region locks
        os_spinlock.h: various spinlocks for the x86_64
        os_thread.{h,cpp}: thread wrapper class
        os_typelock.h: typed locks for C++ 
