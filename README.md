_Note: it is not recommended to import outputs lists into wallets at the time of writing, since it is unlikely that any of these outputs will be selected in your rings at this point. It's more likely that someone will advise you to download a malicious list. Most of these resources were created in 2018 or 2019, so they are likely not very useful for later Monero user behaviors._

Monero is a secure, private cryptocurrency. You can learn more about Monero at [getmonero.org](https://getmonero.org).

`monero-blockhain-mark-spent-outputs` (previously `monero-blockchain-blackball`) is a privacy-enhancing tool that can increase the effectiveness of ring signatures. This tool can be used to avoid including outputs that are known to be spent in other transactions. If you exclude these known-spent outputs, other higher-quality outputs can be included in your ring signatures, thus improving your privacy.

This website contains several resources for running the tool yourself or downloading a blackball database that we have generated. If you care about your privacy and do not want to trust us, then you should run the tool yourself. If you feel comfortable trusting me and favor convenience, you can download the database that we have prepared. It is possible that our databases could reduce your privacy if we are acting maliciously. Furthermore, with large ringsizes, these databases are less necessary.

Keep in mind that a blackball database is only one tool you can use to improve your privacy on Monero. It is not a perfect solution, and it is typically a lagging benefit. For example, if there is an upcoming chain split, a blackball database will provide some protection a few days after the split, but it will not be especially helpful before the split or shortly after. When in doubt, play it safe.

# Running the tool

You can run the `monero-blockhain-mark-spent-outputs` (previously `monero-blockchain-blackball`) tool, available in Monero 0.12 (May 2018) and later, to build a local database. This is strongly recommended if you can take the time to do it.

Unfortunately the tool is a little clunky and slow, so expect it to have some issues and take several days. You should have already synced the full Monero blockchain locally any the blockchains of any Monero forks that you want to test against. You also need a decently fast CPU and hard drive. Luckily, the tool is getting better all the time.

To run the tool, navigate to the latest CLI or GUI tools available on [getmonero.org](https://getmonero.org/downloads). You should see a tool called `monero-blockhain-mark-spent-outputs` (previously `monero-blockchain-blackball`). Open a terminal/command prompt for the following operating systems. You can optionally append `--check-subsets` to perform a more verbose test for a significant decrease in performance. If you want to only check recent outputs that are likely to be selected to save a significant amount of time, run it with `--rct-only`. For old versions, replace `monero-blockhain-mark-spent-outputs` with `monero-blockchain-blackball`.

### Linux / MacOS

`mmonero-blockhain-mark-spent-outputs ~/.bitmonero/lmdb /path/to/other/blockchain/database`

Example: `monero-blockhain-mark-spent-outputs ~/.bitmonero/lmdb /home/monero_fork/lmdb --rct-only`

### Windows

`monero-blockhain-mark-spent-outputs.exe C:\ProgramData\bitmonero\lmdb \path\to\other\blockchain\database`

Example: `monero-blockhain-mark-spent-outputs.exe C:\ProgramData\bitmonero\lmdb C:\ProgramData\monero_fork\lmdb --rct-only`

---

This will export a file that can be added directly to the GUI or CLI. Previous versions [required a conversion](https://monero.stackexchange.com/questions/8225/how-can-i-use-monero-blockchain-blackball-to-improve-my-privacy). 

# Downloading our blackball databases

We offer two blackball (spent output) databases. One is light, small, and only contains recent RingCT (RCT) outputs. The other is a verbose database with as many bad outputs as possible. Check the dates - it's simpler for us to update the smaller databases, so they may be updated more frequently.

### RingCT Only

[Download link](https://github.com/monero-blackball/monero-blackball-site/blob/master/Blackball%20Databases/rct-only/rct-only-2019-03-12)

This file contains outputs from the following:

* Monero from January 2017 through 12 March 2019
* Monerov6 (XMO, XMC) through 12 March 2019
* MoneroV (XMV) through 27 August 2018
* Monerov7 through 12 March 2019
* Monerov9 through 12 March 2019

### Verbose

[Download link](https://github.com/monero-blackball/monero-blackball-site/blob/master/Blackball%20Databases/all/all-2019-03-12)

This file contains outputs from the following:

* Monero through 12 March 2019
* Monerov6 (XMO, XMC) through 12 March 2019
* MoneroV (XMV) through 27 August 2018
* Monerov7 through 12 March 2019
* Monerov9 through 12 March 2019

### Pools

You can also include outputs that are known to be spent in public pool transactions. This file should be used in addition to any of the ones above until they work together (WIP). See [sneurlax's work](https://github.com/sneurlax/xmreuse).

[Direct download link](https://drive.google.com/uc?export=download&id=1bFHsAXkN01tElcjU2dtJuLtqMCU_lDuk)

[Signature file](https://drive.google.com/uc?export=download&id=1xbcmvm2v1l-DVARghCgGInYfz_B3m2gl)

This file contains outputs from the following:

* HashVault through 26 August 2018
* XMRPool through 4 September 2018
* SupportXMR through 27 August 2018

### Instructions for Use

Download the file and place it anywhere.

In the GUI, you can go to Advanced -> Shared RingDB. Then under "Filename with outputs to blackball", select the `rct-only-YYYY-MM-DD` or `all-YYY-MM-DD` file you just downloaded and click `Load`.

In the CLI, run `blackball <filename> add`

Note that the file path in the wallet must not contain any spaces.

### Full Blockchain LMDB Downloads

* monerov through 2018-11-28: [Download Link](https://drive.google.com/drive/folders/1NwT5H2FcDjURuewLdgTz-ol--G6wkvs9?usp=sharing)
* monerov6 through 2019-03-13: [Download Link](https://drive.google.com/drive/folders/1J2igUiwXrOgklcbvu7p3cDbvnzIt2duh?usp=sharing)
* monerov7 through 2019-03-13: [Download Link](https://drive.google.com/drive/folders/1PzhFYc6aX9vYHo1L8sJZJvVz9kZ4fzYi?usp=sharing)
* monerov9 through 2019-03-13: [Download Link](https://drive.google.com/drive/folders/1ScVYeYvKtHUl-VQ8ODD0HU9Fk8k_7vd2?usp=sharing)
* monerov11 through 2019--11-19: [Download Link](https://drive.google.com/drive/folders/1tH2NNxRTYIL8ss7QoVREw_m_-l-vux5V?usp=sharing)

# More Information

https://monero.stackexchange.com/questions/10039/how-can-i-import-a-blackball-database-to-improve-my-privacy/

https://monero.stackexchange.com/questions/8225/how-can-i-use-monero-blockchain-blackball-to-improve-my-privacy/

Twitter: [@JEhrenhofer](https://twitter.com/JEhrenhofer)
