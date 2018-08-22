Monero is a secure, private cryptocurrency. You can learn more about Monero at [getmonero.org](https://getmonero.org).

`monero-blockchain-blackball` is a privacy-enhancing tool that can increase the effectiveness of ring signatures. This tool can be used to avoid including outputs that are known to be spent in other transactions. If you exclude these known-spent outputs, other higher-quality outputs can be included in your ring signatures, thus improving your privacy.

This website contains several resources for running the tool yourself or downloading a blackball database that we have generated. If you care about your privacy and do not want to trust us, then you should run the tool yourself. If you feel comfortable trusting me and favor convenience, you can download the database that we have prepared. It is possible that our databases could reduce your privacy if we are acting maliciously.

Keep in mind that a blackball database is only one tool you can use to improve your privacy on Monero. It is not a perfect solution, and it is typically a lagging benefit. For example, if there is an upcoming chain split, a blackball database will provide some protection a few days after the split, but it will not be especially helpful before the split or shortly after. When in doubt, play it safe.

# Running monero-blockchain-blackball

You can run the `monero-blockchain-blackball` tool, available in Monero 0.12 (May 2018) and later, to build a local database. This is strongly recommended if you can take the time to do it.

Unfortunately the tool is a little clunky and slow, so expect it to have some issues and take several days. You should have already synced the full Monero blockchain locally any the blockchains of any Monero forks that you want to test against. You also need a decently fast CPU and hard drive. Luckily, the tool is getting better all the time.

To run the tool, navigate to the latest CLI or GUI tools available on [getmonero.org](https://getmonero.org/downloads). You should see a tool called `monero-blockchain-blackball`. Open a terminal/command prompt for the following operating systems. You can optionally append `--check-subsets` to perform a more verbose test for a significant decrease in performance. If you want to only check recent outputs that are likely to be selected to save a significant amount of time, run it with `--rct-only`.

### Linux / MacOS

`monero-blockchain-blackball ~/.bitmonero/lmdb /path/to/other/blockchain/database`

Example: `monero-blockchain-blackball ~/.bitmonero/lmdb /home/monero_fork/lmdb --rct-only`

### Windows

`monero-blockchain-blackball.exe C:\ProgramData\bitmonero\lmdb \path\to\other\blockchain\database`

Example: `monero-blockchain-blackball.exe C:\ProgramData\bitmonero\lmdb C:\ProgramData\monero_fork\lmdb --rct-only`

---

Now, the file needs to be converted to work with the wallet software. Follow [these steps](https://monero.stackexchange.com/questions/8225/how-can-i-use-monero-blockchain-blackball-to-improve-my-privacy/) to convert the file to a wallet-readable format. This is honestly the most tricky part.

# Downloading our blackball databases

We offer two blackball databases. One is light, small, and only contains recent RingCT (RCT) outputs. The other is a verbose database with as many bad outputs as possible. If you are worried about attacks on the network such as chain splits, check the dates to make sure they are recent. The RingCT-only database may be more effective, since it is smaller and can be updated more easily.

### RingCT Only

[Direct download link](https://drive.google.com/uc?export=download&id=1r1h9hEVzJN5XsUnsCnfGesWmzovRE3Qo)

[Signature file](https://drive.google.com/uc?export=download&id=1-HCabvc9CNQnb87msJFrbSwx83OKPCbc)

This file contains outputs from the following:

* Monero from January 2017 through 20 August 2018
* Monerov6 (XMO, XMC) through 15 August 2018

### Verbose

[Direct download link](https://drive.google.com/uc?export=download&id=1zPer9BqsIno8ZI_RMQuRFehiAdx8kbyZ)

[Signature file](https://drive.google.com/uc?export=download&id=1yr0yhWSmK4Ng1IAY8RDlY048OAZ0uoQo)

This file contains outputs from the following:

* Monero through 20 August 2018
* Monerov6 (XMO, XMC) through 15 August 2018

### Instructions for Use

Download the file and place it anywhere.

In the GUI, you can go to Advanced -> Shared RingDB. Then under "Filename with outputs to blackball", select the `rct-only.txt` or `all.txt` file you just downloaded and click `Load`.

In the CLI, run `blackball <filename> add`

Note that the file path in the wallet must not contain any spaces.

# More Information

https://monero.stackexchange.com/questions/10039/how-can-i-import-a-blackball-database-to-improve-my-privacy/

https://monero.stackexchange.com/questions/8225/how-can-i-use-monero-blockchain-blackball-to-improve-my-privacy/

Twitter: [@JEhrenhofer](https://twitter.com/JEhrenhofer)
