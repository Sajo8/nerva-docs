# Setting Up a Paper Wallet

The main purpose of a paper wallet is to quickly create a wallet to start receiving funds. 

**You will not be able to spend or send your funds to other people until you set up a CLI wallet on an internet-connected machine**

You can view a guide on how to make a wallet [here](Using-the-CLI-Wallet)

There are two options for a paper wallet.

## Making A Paper Wallet on an Internet-Connected Machine

Go to [this link](https://getnerva.org/paperwallet/index.html) and follow [these steps.](#generating-the-wallet)

## Making a Paper Wallet on an Air-Gapped Machine

Go to [this GitHub repository](https://bitbucket.org/nerva-project/website/downloads/?tab=downloads)(on a machine connected to the internet).

To use it, follow these steps:

**Windows**
  - Click on `Download repository`

  - Extract the `.zip` file to a directory of your choice (say, `C:/paper`)

  - Copy/paste the files through a flash drive to your air-gapped machine.

  - Open the folder where you pasted the files, (say `C:/paper`) 
  
  - Navigate to `.../paperwallet/` (`C:/paper/paperwallet`)

  - Double click on `index.html`

  - Follow [these steps.](#generating-the-wallet)

**Linux**
  - Open the terminal

  -  Install git if it's not already installed (`apt-install git`)

  - Type, `git clone https://bitbucket.org/nerva-project/website.git nerva-paper-wallet`and press enter

  - Then enter `cd nerva-paper-wallet/paperwallet`

  - After doing so, enter `index.html`

  - A page should open up in your browser

  - Follow [these steps.](#generating-the-wallet)

### Generating the Wallet

- Click on `GENERATE WALLET`

- The letters and numbers in the green box, starting with `NV`, is your public address. You can share it freely. 

- Save the `Mnemonic seed`, the 25 words in the *red* box, safely.  
**DO NOT SHARE IT WITH ANYONE**.  
**Anyone who has access to this can *access your funds* and has *complete control* over your wallet.**

- Save the `Spend Key` and the `View Key`, the two very long strings of (seemingly) random letters and numbers, in the *blue* box, safely.  
**DO NOT SHARE IT WITH ANYONE**.  
**Anyone who has access to this can *access your funds* and has *complete control* over your wallet.**
