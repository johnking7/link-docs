###########
Obtain LINK
###########

In order to publish content on the Link network, or execute any kind of transaction, you must spend some LINK. LINK can be obtained either by mining it or by purchasing it.

You need to have a Link account. If you do not have one already, go to the Link console and run ``personal.newAccount();``.

Alternatively an Ethereum account can be created with `MyEtherWallet <https://www.myetherwallet.com/>`_ and that can be used for Link.

Mine LINK
---------

CPU Mining
##########

CPU mining with Geth is very easy. Run the regular Geth command, but add the ``--mine`` option. Use ``--etherbase`` to specify which account will receive the mining rewards. It defaults to using all processor cores. This can be changed using the ``--minerthreads`` option.

GPU Mining
##########

Use `ethminer-genoil <https://github.com/Genoil/cpp-ethereum>`_.

Ubuntu 15.10 or Newer. OpenCL only (for AMD cards)
.. code::

  sudo apt-get update
  sudo apt-get -y install software-properties-common
  add-apt-repository -y ppa:ethereum/ethereum
  sudo apt-get update
  sudo apt-get install git cmake libcryptopp-dev libleveldb-dev libjsoncpp-dev libjsonrpccpp-dev libboost-all-dev libgmp-dev libreadline-dev libcurl4-gnutls-dev ocl-icd-libopencl1 opencl-headers mesa-common-dev libmicrohttpd-dev build-essential -y
  git clone https://github.com/Genoil/cpp-ethereum/
  cd cpp-ethereum/
  mkdir build
  cd build
  cmake -DBUNDLE=miner ..
  make -j8
  
  
Ubuntu 15.10 or Newer. OpenCL + CUDA (for NVIDIA cards)
.. code::

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

You can then find the executable in the ethminer subfolder

Purchase LINK
-------------
LINK from the revenue smart contract will be sold on exchanges once they support it. Until then, LINK can be purchased directly.

If you wish to purchase LINK please email purchase@link-blockchain.org. It is currently available at a price of 0.01 USD per LINK. This price is subject to change at any time. Payment can be made via any cryptocurrency.
