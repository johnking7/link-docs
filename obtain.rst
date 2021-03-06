###########
Obtain LINK
###########

In order to publish content on the LINK network, or execute any kind of transaction, you must spend some LINK. LINK can be obtained either by mining it or by purchasing it.

You need to have a LINK account. If you do not have one already, go to the LINK console and run ``personal.newAccount();``.

Alternatively an Ethereum account can be created with `MyEtherWallet <https://www.myetherwallet.com/>`_ and that can be used for LINK.

Mine LINK
---------

CPU Mining
##########

CPU mining with Geth is very easy. Run the regular Geth command, but add the ``--mine`` option. Use ``--etherbase`` to specify which account will receive the mining rewards. It defaults to using all processor cores. This can be changed using the ``--minerthreads`` option.

GPU Mining
##########

Genoil
``````

Ubuntu 15.10 or Newer. OpenCL only (for AMD cards)
::

  sudo apt-get update
  sudo apt-get -y install software-properties-common
  sudo add-apt-repository -y ppa:ethereum/ethereum
  sudo apt-get update
  sudo apt-get install git cmake libcryptopp-dev libleveldb-dev libjsoncpp-dev libjsonrpccpp-dev libboost-all-dev libgmp-dev libreadline-dev libcurl4-gnutls-dev ocl-icd-libopencl1 opencl-headers mesa-common-dev libmicrohttpd-dev build-essential -y
  git clone https://github.com/Genoil/cpp-ethereum/
  cd cpp-ethereum/
  mkdir build
  cd build
  cmake -DBUNDLE=miner ..
  make -j8
  
  
Ubuntu 15.10 or Newer. OpenCL + CUDA (for NVIDIA cards)
::

  wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1404/x86_64/cuda-repo-ubuntu1404_7.5-18_amd64.deb
  sudo dpkg -i cuda-repo-ubuntu1404_7.5-18_amd64.deb
  sudo apt-get -y install software-properties-common
  sudo add-apt-repository -y ppa:ethereum/ethereum
  sudo apt-get update
  sudo apt-get install git cmake libcryptopp-dev libleveldb-dev libjsoncpp-dev libjsonrpccpp-dev libboost-all-dev libgmp-dev libreadline-dev libcurl4-gnutls-dev ocl-icd-libopencl1 opencl-headers mesa-common-dev libmicrohttpd-dev build-essential cuda -y
  git clone https://github.com/Genoil/cpp-ethereum/
  cd cpp-ethereum/
  mkdir build
  cd build
  cmake -DBUNDLE=cudaminer ..
  make -j8

CD to the ``ethminer`` subfolder and run the following command
::

  ./ethminer -G -F http://localhost:8645

Claymore
````````
Download from https://github.com/nanopool/Claymore-Dual-Miner/releases

Linux
::

  ./ethdcrminer64 -epool http://localhost:8645 -allcoins exp

Windows
::

  EthDcrMiner64.exe -epool http://localhost:8645 -allcoins exp

Here is a Claymore on Windows LINK mining tutorial: https://klmoney.wordpress.com/link-blockchain-windows-gpu-mining/

Purchase LINK
-------------
LINK is not yet trading on any exchange.

If you wish to purchase LINK please email purchase@link-blockchain.org. It is currently available at a price of 0.04 USD per LINK. This price is subject to change at any time. Payment can be made via any cryptocurrency.
