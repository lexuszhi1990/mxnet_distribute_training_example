python launch.py -n 2 -H hosts --sync-dst-dir /tmp/mxnet python train_mnist.py --network lenet --kv-store dist_sync

ssh -o StrictHostKeyChecking=no intellif@192.168.2.46 -p 22
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:/usr/lib/x86_64-linux-gnu:/usr/local/lib:/usr/local/cuda/lib64:/usr/lib/x86_64-linux-gnu:/usr/local/lib:; export DMLC_ROLE=worker; export DMLC_PS_ROOT_PORT=9096; export DMLC_PS_ROOT_URI=192.168.2.177; export DMLC_NUM_SERVER=2; export DMLC_NUM_WORKER=2; cd /tmp/mxnet;python train_mnist.py --network lenet --kv-store dist_sync
