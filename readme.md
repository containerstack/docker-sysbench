## Debian Jessie based Sysbench Docker container

### CPU benchmark
sysbench --test=cpu --num-threads=4 --cpu-max-prime=20000 run

### Disk IO benchmark
#### Create test file that is bigger than the RAM size for example RAM=16GB --> TestFile=32GB
sysbench --test=fileio --file-total-size=20G prepare

#### Run benchmark
sysbench --test=fileio --file-total-size=150G --file-test-mode=rndrw --init-rng=on --max-time=300 --max-requests=0 run

### Memory benchmark
sysbench --test=memory --memory-block-size=1M --memory-total-size=10G run

### Help info
sysbench --help
