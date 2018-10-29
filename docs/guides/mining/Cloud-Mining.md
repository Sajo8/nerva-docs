# How to Mine NERVA with Google Cloud Platform (GCP)

## Setting Up the VM(Virtual Machine)

1.  Go [here](https://console.cloud.google.com/freetrial) and sign in with your Google Account. Enter the details requested to sign up for the free trial.  
    *You will need a valid credit card to sign up for it*
2.  After signing up, go [here](https://console.cloud.google.com/compute/instances)
3.  If it asks you for a project name, enter one or let it be the defualt one, it doesn't really matter.
4.  On the top, click `CREATE INSTANCE`
5.  Give it a name, just one so that you can remember what it is and you can differentiate between the VM's you set up
6.  Choose a zone. Any zone will do, doesn't really matter.
    **Note: For every VM, you must choose a different zone. If `instance-1` has zone `us-east1-b`, then `instance-2` must have `us-west1-b` and `instance-3` must have `us-central1-b`, and so on and so forth.**
7.  Under `Machine Type` click `Customize`.
8.  Change `Cores` to `4` and `Memory` to `3.6 GB`. Change `CPU platform` to `Intel Skylake or later`
9.  Leave the rest as is, and click double check both `Allow HTTP traffic` and `Allow HTTPS traffic`
10. Click `Create`
11. Follow [instructions for setting it up](#instruct-set-up-linux)

## Mining Instructions For Debian Linux on GCP <a name="instruct-set-up-linux"></a>

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

## Detaching it From the Shell

When you close the SSH window, the mining will also stop. To prevent this, follow these steps-

1.  Close nervad if it's running by entering `Ctrl + C` on your keyboard
2.  Type `clear`
3.  Type `screen`
4.  Press enter
5.  Type `./nervad` to launch the daemon
6.  Run the `start_mining` command with your address and number of threads
7.  Once it starts mining, press `Ctrl + A` and `Ctrl + D` on your keyboard to detach it.

You can now close the SSH window safely

To restore the detached window, type-

`screen -r`
