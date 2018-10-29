# How to Set Up XMR-Stak on Linux

Native binaries may be available for your distribution's package manager.

If no binaries are available, or you prefer to compile, follow these instructions-

## Ubuntu 16.04/17.10/18.04<a name="ubuntu-16-04"></a>

1.  Open the terminal and install dependencies by running this command-

    ```
    sudo apt install -y build-essential cmake pkg-config libboost-all-dev libssl-dev libzmq3-dev libunbound-dev libsodium-dev libcurl4-openssl-dev libminiupnpc-dev libunwind8-dev liblzma-dev libreadline6-dev libldns-dev libexpat1-dev libgtest-dev doxygen graphviz
    ```

2.  Clone the package-

    `git clone --recursive https://bitbucket.org/nerva-project/nerva`

3. CD to the cloned directory

    `cd nerva`

5.  Make a directory-

    `mkdir ./build && cd ./build`

6.  Run cmake-

    `cmake -D CMAKE_BUILD_TYPE=Release -D BUILD_SHARED_LIBS=OFF ..`

7.  Finish building it-

    `make`

8.  The core software will now be located in `~/nerva/build/bin`

9.  Type-

    `./nervad`

10. Wait for it to finish syncing

    It will display:

    ```
    **********************************************************************
    You are now synchronized with the network. You may now start nerva-wallet-cli.

    Use the "help" command to see the list of available commands.
    **********************************************************************
    ```

11. See [Setup and Configuration](#setup-and-config)

## Solo-Miner Setup and Configuration<a name="setup-and-config"></a>

Upon finishing syncing with the network, type in the following command:

```
start_mining NV... 4
```
Replace `NV...` with your NERVA address and `4` with however many threads you would like to mine with.  
We recommend mining with half as many as threads you have; so if you have 8 threads, enter `4`

For example:

```
start_mining NV2c9tuqUNRZNK4i6jahuPaDSnfYFRAcyW7t13aox32yUkWwbpTHxXYbtgYR8qQ4hPB2t5EqJZwt7fS1kyHvrHap1GrFt6fM8 4
```

Done! The miner will now begin mining. Awesome!

To re-launch the miner:  
1. Open `nervad`
2. Wait for it to finish syncing
3. Run the `start_mining` command