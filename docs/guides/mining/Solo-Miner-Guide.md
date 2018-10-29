# How to Set Up the Solo Miner

The solo-miner is in-built into the core software, letting you check your balance and mine at the same time.  
Please know that you can only mine with *your CPU* on NERVA, and *cannot* use your GPU to mine NERVA

## Downloading and Installing for Windows

1. Download and install [the NERVA core software](https://getnerva.org/#downloads)(click "Windows").

2. Make a folder called `NERVA` on your Desktop and unzip the files you just downloaded for the core software in there.

3. Double-click on `nervad.exe`.

4. Wait for it to finish syncing

    It will display:

    ```
    **********************************************************************
    You are now synchronized with the network. You may now start nerva-wallet-cli.

    Use the "help" command to see the list of available commands.
    **********************************************************************
    ```

5. See [Setup and Configuration](#setup-and-config)

## Downloading and Installing for Mac

Coming soon!

## Downloading and Installing for Linux

View [this guide](../Solo-Miner-Linux-Guide) to get started with solo mining on Linux.

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
