# FAQ Regarding Bitcoin Seeds
By [6102bitcoin](https://twitter.com/6102bitcoin)

## Index

1) [**The Basics**](#1-The-Basics)
	- [Introduction](#Introduction)
	- [Terminology](#Terminology)
	- [What is a HD Wallet?](#What-is-a-HD-Wallet)
2) [**Creating your seed**](#2-Creating-your-seed)
	- [Where should I physically be when I backup my seed?](#Where-should-I-physically-be-when-I-backup-my-seed)
	- [All seeds are not created equal](#All-seeds-are-not-created-equal)
	- [Does the order of the words matter?](#Does-the-order-of-the-words-matter)
	- [How do I get my seed?](#How-do-I-get-my-seed)
	- [Should I check my seed?](#Should-I-check-my-seed)
3) [**Storing your Seed**](#3-Storing-your-Seed)
	- [Why should I bother storing my seed, I only have a small amount of bitcoin?](#Why-should-I-bother-storing-my-seed-I-only-have-a-small-amount-of-bitcoin)
	- [Should I have multiple (redundant) backups?](#should-i-have-multiple-redundant-backups-of-my-seed)
	- [How can I store my seed](#How-can-I-store-my-seed)
	- [Can I 'encrypt' my seed so that all is not lost if someone finds my mnemonic?](#Can-I-encrypt-my-seed-so-that-all-is-not-lost-if-someone-finds-my-mnemonic)
	- [Paper Backups](#Paper-Backups)
	- [Metal Backups](#Metal-Backups)
	- [Should I split my mnemonic in two (short version)?](#should-i-split-my-mnemonic-in-two-short-version)
	- [Should I split my mnemonic in two (long version)?](#should-i-split-my-mnemonic-in-two-long-version)
	- [Should I split my seed ABC into AB|BC|CA?](#should-i-split-my-seed-abc-into-abbcca)
	
4) [**Using your Seed**](#4-Using-your-Seed)
	- [Can I recover my bitcoin without my seed?](#Can-I-recover-my-bitcoin-without-my-seed)
	- [Can I recover my bitcoin without my passphrase?](#Can-I-recover-my-bitcoin-without-my-passphrase)
	- [I have forgotten my passphrase, what now?](#I-have-forgotten-my-passphrase-what-now)
	- [How should I recover bitcoin using my seed?](#How-should-I-recover-bitcoin-using-my-seed)
	- [What is the Derivation Path?](#What-is-the-Derivation-Path)
	- [How often should I check backups?](#how-often-should-i-check-backups)

# 1) The Basics

### Introduction

Great - you have decided to control your bitcoin directly instead of using a custodial service like an exchange. This is a very wise move - exchanges fall into only two categories; those which have been hacked and those which will be hacked.

By holding your own keys, you (and only you) are able to spend your bitcoin. You should take time to read this FAQ in order to understand the common errors & mistakes, and to learn the best practice in seed management. Be aware that this a general guideline. Every solution for storing your bitcoin seed will be a tradeoff between security and usability, and the level of security needed or wanted will vary from person to person, as will the threats you are trying to secure yourself against.

### Terminology

When it comes to bitcoin seed descriptions, words are often confused and used interchangeably. It is important that we speak a common language, so let me define what I mean by each of these words.

| Word | Definition | Other Names |
| ---- | ---- | ---- |
| [**Private Key**](https://en.bitcoin.it/wiki/Private_key) | A secret 256 bit number that you use to spend bitcoin | Secret Key | 
| [**Seed**](https://en.bitcoin.it/wiki/Seed_phrase) | A 256 bit number which can be used to generate a bitcoin private key. |  |
| **Mnemonic Seed** | The seed encoded in the form of a list of words in a specific order.  | Mnemonic / Seed Phrase / Seed Words |
| **Non-Extended Mnemonic** | 12/24 Words (Just the Mnemonic) | Mnemonic  | 
| **Extended Mnemonic** | 12+/24+ Words: Mnemonic (12/24 words) + Passphrase (1 word or sentence) | Extended Seed | 
| **Backup** | A complete set of information from which your bitcoin can be recovered  | |
| **Encrypted Backup** | Backup encrypted with a password (not to be confused with a passphrase) | |

### What is a HD Wallet?

In practice, most bitcoin wallets are 'HD' (Hierarchical Deterministic) wallets - This means that a single bitcoin private key is used to generate as many key pairs as is required. This makes it easy for the user to use a new address each time they receive bitcoin, which is how bitcoin is designed to be used. 

With a HD wallet the bitcoin private key (which is derived from the seed) is combined with something called a 'chain code' to generate what is referred  to as a 'master extended key'. For more details see [BIP32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki).

Typically you are presented with a mnemonic seed, a series of either 12 or 24 words from [this list](https://github.com/bitcoin/bips/blob/master/bip-0039/english.txt) - it is an encoded version of your seed made to be easy to read and store. The encoding method is detailed in [BIP39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki#), but effectively each word on the wordlist corresponds with a number, and thus your 12 word mnemonic is simply an easy to write representation of a large number (your seed). 

Many wallets carelessly label the mnemonic seed as just the 'seed' - take care, the mnemonic seed can be extended with an additional word or sentence (a passphrase), without which you cannot decode the actual seed (a 256 bit number) and thus, you cannot recover your bitcoin.

All seeds encoded using BIP39 actually consist of the mnemonic + a passphrase. More secure wallets (e.g Samourai Wallet) will give you the option to set a passphrase (not to be confused with a password). **If you use a passphrase and then forget it you will lose your bitcoin.**

Again, because people repeatedly make this mistake: **If you set a passphrase, and forget it, you can't recover your bitcoin!**

Anyone with access to your seed can spend your coins.
As such it is imperative that you store copies of your seed securely. 

# 2) Creating your Seed

### Where should I physically be when I backup my seed?

Remember that if anyone sees your seed it is potentially compromised, and should be treated as such. 
For this reason make sure that you backup your seed somewhere that is private and that has no cameras/CCTV. 
- Don't read your seed aloud as someone could hear it. 
- Don't type it into a computer
- Don't take a picture / screenshot

### All seeds are not created equal

Suppose you have a computer riddled with malware and viruses and you download some bitcoin wallet software and view the seed (or more likely the mnemonic seed). This seed is likely insecure. The viruses/malware may be taking screenshots of your computer at regular intervals and sending this data to the creator of the virus/malware. 
If you can see your seed on screen, then potentially so can the hacker.

For this reason, with non-trivial amounts of bitcoin it is crucial that you carefully control the environment in which the seed is generated. The easiest way for non-technical people to do this is to buy a 'Hardware Wallet'. These devices store all the 'secret information' required to access your bitcoin on the dedicated hardware device so that it doesn't matter if your computer has viruses/malware. 

That said, some hardware wallets are better than others so make sure that you never enter your seed into your computer - only enter it into the device itself.

Another option is to generate a seed using a clean computer which is not connected to the Internet.

### Does the order of the words matter?
Yes! The order of the words in a mnemonic seed does matter. You must store your mnemonic seed in such a way that the order of the words is clear and unambiguous. Remember - the mnemonic seed is simply an encoding of the seed which is a large number, if you get the order wrong then you will decode a different number.

### How do I get my seed?

This will depend on the bitcoin wallet that you are using. Most have a 'backup seed' option visible in the settings menu which can be used at any time, though some only allow seed backups when the wallet is initialised. Again, what you are backing up is typically the mnemonic seed. If you use an extended mnemonic (i.e. A 12/24 word mnemonic seed + a passphrase) you MUST have access to the passphrase to recover your bitcoin. For this reason it is very important to backup your passphrase in addition to your seed - though you should not store them in the same place.

It is important to note that it is generally insecure to create your own seed as humans are not good at creating truly random information. 

### Should I check my seed?

You should definitely check your backup as part of your process for backing up. Failure to do so could lead to you losing your bitcoin - don't risk it. Part of checking the backup is checking that you have correctly recorded your seed, though this is not the whole process. You should additionally check that you know the derivation path the passphrase (if you used one).

# 3) Storing your Seed

### Why should I bother storing my seed, I only have a small amount of bitcoin.

The value of bitcoin could increase substantially and you may one day regret not backing up your seed. You should **always** back up your seed. It is good practice to regularly review your seed management and consider how effective your chosen solution is.

### Should I have multiple (redundant) backups of my seed?

Yes. For the reasons explained below you should have multiple redundant backups of your seed.

### How can I store my seed?
Initially let us consider the case where you store a single unencrypted mnemonic seed (12 or 24 words). 

| Method  						   	|Location          				| Digital Theft Resistance 	| Physical Theft Resistance 		| Durability 						|
| ------    					    | ---- 				    		| -------------------------	| ------------------------------|	---------------				|
| Screenshot              | On Phone 					  | Weak							        | Weak													|	Fragile (Deletion) 		|
| Notes App               | On Phone					  | Weak							        | Weak													|	Fragile (Deletion)		|
| Printed Paper Note  		| In Home 					  | Weak							        | Weak													|	Fragile (Fire)	  		|
| Printed Paper Note 			| Bank Deposit Box 		| Weak							        | **Strong**										|	**Durable**        		|
| Handwritten Paper Note  | In Home 					  | **Strong**				        | Weak													|	Fragile (Fire)	  		|
| Handwritten Paper Note  | Bank Deposit Box 		| **Strong**				        | **Strong**										|	**Durable**        		|
| Handwritten Paper Note  | Buried Somewhere 		| **Strong**				        | **Strong**										|	Fragile (Water)				|
| Stamped Metal Sheet [1]	| In Home 					  | **Strong**				        | Weak													|	**Durable**        		|
| Stamped Metal Sheet	    | Bank Deposit Box 		| **Strong**				        | **Strong**										|	**Durable**        		|
| Stamped Metal Sheet	    | Buried Somewhere 		| **Strong**				        | **Strong**										|	**Durable**        		|
| USB (Plaintext)					| In Home 						| **Strong**				        | Weak													|	Fragile (Water/Time)	|
| Memorised	[2]						| Brain								| **Strong**				        | **Strong**										|	Fragile (Time/Injury)	|

*[1] There are many ways to do this, some are better than others - see Lopp's [initial comparison](https://medium.com/@lopp/metal-bitcoin-seed-storage-stress-test-21f47cf8e6f5) & more recent comparison: [Medium](https://medium.com/@lopp/metal-bitcoin-seed-storage-stress-test-part-ii-d309e04aefeb) [Youtube](https://youtu.be/zFN__b6ARH4?t=20593)*

*[2] Often referred  to as a [Brain Wallet](https://en.bitcoin.it/wiki/Brainwallet) - Not to be confused with a wallet where you generate the mnemonic using your brain (i.e. sentence from a book) a Brain Wallet is a wallet with a memorised mnemonic which was generated securely using a source of entropy.*

There are three methods that are both Resistant to Theft and Durable;
- Handwritten Paper Note in a Bank Deposit Box
- Stamped Metal Sheet in a Bank Deposit Box
- Stamped Metal Sheet Buried Somewhere

A Bank Deposit Box is fine, but it requires some degree of trust in the bank.
Burying is fine, but it requires some degree of luck that someone won't find it / that you will be able to find it.

In either case, theft of the mnemonic seed can occur. Theft of an unencrypted seed is bad for two reasons;
A) The thief can spend your coins at any time. If they replace the seed there is no way for you to know that the seed is compromised. 
B) You have lost your backup. You are unable to restore your seed, thus your bitcoin is lost whether or not the thief sweeps the funds. 

You can use a watch only wallet to monitor the balance of your addresses, though if you see your funds move it is too late to do anything about it. Furthermore, if someone finds your watch only wallet they know how much bitcoin you have.

If you notice that your seed has been stolen you want to be able to quickly move your funds in-case the thief hasn't figured out what they stole, or they simply haven't swept the funds yet. For this reason is obvious that you should have MULTIPLE seed backups.

But with an **unencrypted seed**, each additional backup is an additional risk, because theft of any one of your backups is enough for a thief to steal your bitcoin. It would be better if you encrypted your seed, so that the thief wouldn't be able to steal your funds if they only have your 12/24 word mnemonic. 

### Can I 'encrypt' my seed so that all is not lost if someone finds my mnemonic?

Yes, you can encrypt your seed by one of two methods:

#### 1) Use a passphrase alongside your mnemonic seed following [BIP39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki#from-mnemonic-to-seed)

Behind the scenes, all wallets following BIP39 (pretty much all wallets) are actually using a passphrase of "" (an empty string). 
Some wallets will let you set a custom passphrase which combined with your mnemonic forms your seed.
	
Note, the passphrase is sometimes referred to as a "seed extension", "extension word" or "the 13th/25th word".

#### 2) Encrypt the plaintext seed words

You can take your mnemonic seed and use any encryption method to ensure that you need to use a password to decrypt the file. 
You use either Physical or Digital Encryption Tools;

- **Physical Encryption Tool** ([e.g. Enigma](https://en.wikipedia.org/wiki/Enigma_machine) / [One Time Pad](https://en.wikipedia.org/wiki/One-time_pad)): Clearly if you are using a physical encryption tool you will need to ensure that the tool is commonly available so that you can decode when required. Enigma Machines are hard to come by - so they are not a practical solution. The One Time Pad provides perfect encryption, but remember - anyone with physical access to the pad can decode the mnemonic.
- **Digital Encryption Tool** ([e.g. VeraCrypt](https://www.veracrypt.fr/en/Home.html)): If you are using a digital encryption tool you will need to ensure that the computer on which you are encrypting/decrypting data is secure. The easiest way to do this is to use a temporary OS like [tails](https://tails.boum.org) on an old computer which is not connected to the Internet. 
	
### Paper Backups

If you do decide to use a paper backup:
- Use waterproof ink & paper
- Write on a hard surface so you don't indent the paper below
- You can increase the durability of your paper backup by laminating it
- Consider labelling your seed discreetly. Something labelled 'BITCOIN SEED' is more likely to be swept (stolen) than if you label it 'COOKIE RECEPIE', though it may be easy to forget that you did this. 
- Laminate the paper

Learn More: [Here](https://www.quora.com/How-do-I-maintain-a-paper-notebook-that-can-remain-for-years) and [Here](https://www.quora.com/If-I-write-with-a-pencil-on-my-notebook-will-the-writing-last-for-a-long-time-say-50-years-or-will-it-just-fade-away-gradually)

### Metal Backups

There are lots of options available. See Lopp's [initial comparison](https://medium.com/@lopp/metal-bitcoin-seed-storage-stress-test-21f47cf8e6f5) & [more recent comparison](https://youtu.be/zFN__b6ARH4?t=20593).
The [Blockplate 1.0](https://www.blockplate.com/) appears to hold up well to fire / crushing while being easy to use.

### Should I split my mnemonic in two (short version)?

This reduces the cryptographic security of your backup (it is far easier to brute force the private key with half the mnemonic words already known than with none known). 

That said, the thief would have to know what the words are and either spend time cracking the seed themselves or sell the words to someone who would have no way to know the bitcoin they could steal before cracking the seed (so may be unwilling to pay for the first/last words).

If you are going to do this be sure to use a 24 word mnemonic seed (not a 12 word mnemonic seed). 

It is better to use [Shamir's secret sharing](https://en.wikipedia.org/wiki/Shamir%27s_Secret_Sharing) to split the seed into 2 secrets, this way each piece of information is useless in isolation, and it is impossible to brute force the private key. The secrets can be recombined to recover the seed. You can also add redundancy, requiring say 2 of 3 of the secrets, or 3 of 5 (or any N of M). TailsOS comes with a pre-installed commandline tool called [ssss](http://point-at-infinity.org/ssss/) for this purpose. 
Please let me know ([@6102bitcoin](https://twitter.com/6102bitcoin)) if you can recommend any others.

### Should I split my mnemonic in two (long version)?

If an attacker knows the first/last 12 words of a 24 word seed the security against a brute force attack is greatly reduced (compared to brute forcing with none of the words known). Importantly it is more than twice as easy to brute force the half known seed (to understand without going into too much detail consider that 2^24 is 4096 times greater than 2^12).

All else being equal you should make it impossible for an attacker to access to any of your seed words.

In reality, all else is often not equal. It is important to consider the relative security of the options available to an individual when discussing bitcoin seed security. 

Take Alice & Bob;
- Alice stores a full copy of her seed (24 words) in location A and a second full copy of her seed (24 words) in location B.
- Bob stores half his seed (12 words) in location A and the other half (12 words) in location B.

If an attacker (Charlie) goes to location A he can easily steal Alice's bitcoin with minimal effort or technical expertise - he simply has to identify that what he has found is a bitcoin seed and use a tool to try different derivation paths for the seed until he finds bitcoin to steal.

For Charlie to steal bob's bitcoin he will have to identify that he has found half a bitcoin wallet and then brute force the remaining 12 words. It is possible that he would be able to brute force Bob's seed given enough time, but it is also possible that the attacked would not be technically competent enough to brute force the seed, or that he wouldn't even realise that he has 12 words of a 24 word seed (perhaps he would assume that it's an invalid 12 word seed).

It would be natural to conclude that Bob's bitcoin seed is more secure than Alice's.

But now consider what would happen if Charlie is an arsonist (not a thief) and he sets location A on fire.

Regardless of how Alice stored her seed (on paper, stamped on metal etc.) she has a full backup in location B - she does not lose her bitcoin.
For Bob, how he stored his seed is now essential. He has no full backups, no redundancy. If the seed in location A is lost then so are all his bitcoin. Even if he stamped his seed into a metal plate it is possible that location A is an old building which collapsed in the fire, and his metal plate is buried under tonnes of brick and iron.

It would be natural to conclude that Alice's bitcoin are more secure then Bob's.

This example was simply meant to highlight that it is easy to forget that there are often trade-offs when it comes to securing your bitcoin seed. Though you should take care to minimise the risks posed by a sophisticated attacker capable of brute forcing half a 24 word seed you should first limit your exposure to risks which are more likely to pose a realistic threat (such as fire / malware / social attacks). 

### Should I split my seed ABC into AB|BC|CA?

People will suggest using 3 partial seeds to a 24 word mnemonic seed, each with 16 words i.e. [1-16] , [9-24] , [17-24 & 1-8]. This does give some redundancy, but as discussed previously the relationship between number of revealed seed words and security against brute force attack is not linear. 

As a simple exercise to compare of relative strength of 24, 12 and 8 unknown bits (0/1) compare the number of combinations possible. 2^24 = 16777216, 2^12 = 4096, 2^8 = 256. 

There are ~ 4000 times fewer combinations of 12 bits than there are 24 bits, and ~65000 times fewer combinations of 8 bits than 24 bits. Other people will be able to crunch the actual numbers for BIP38 seeds, and it may be that the security of this method is still sufficiently high that it is a reasonable approach for almost everyone (excluding those which huge bitcoin holdings).   

This method (splitting seed into three 2/3 pieces) is simple, and does not require evaluation of any additional code (as is required for Shamir's Secret Sharing) but it does significantly lower the security against brute force attacks.

# 4) Using your seed

### Can I recover my bitcoin without my seed?
No. It is not possible to recover your bitcoin unless you have your seed. **Lose your seed, Lose your bitcoin**.

### Can I recover my bitcoin without my passphrase?
No. If you used a passphrase is not possible to recover your bitcoin unless you have BOTH your mnemonic seed AND your passphrase. **Lose your passphrase, Lose your bitcoin**.

### I have forgotten my passphrase, what now?
If you still have access to your wallet (say you are using Samourai Wallet on your mobile and you can get into an existing wallet with your PIN code) you should consider IMMEDIATELY sending your bitcoin to a new wallet for which you have backups of both the Mnemonic Seed AND the passphrase. 
Be aware that you damage your privacy by consolidating UTXO's. It may be prudent to;
- Mark all UTXO's as 'do not spend' excluding one UTXO
- Send your max balance to a new address generated using your new wallet (with a new, backed up Mnemonic seed & Passphrase).
- Once sent, unmark another UTXO
- Send that to a second, new address generated using your new wallet 
- Repeat

### How should I recover bitcoin using my seed?

You should follow the same rules when recovering bitcoin using your seed as when you are generating your seed;
- Carefully control the environment in which the seed is exposed. The easiest way for non-technical people to do this is to buy a 'Hardware Wallet'. These devices store all the 'secret information' required to access your bitcoin on the dedicated hardware device so that it doesn't matter if your computer has viruses/malware. That said, some hardware wallets are better than others so make sure that you never enter your seed into your computer - only enter it into the device itself.

Remember that if anyone sees your seed it is potentially compromised, and should be treated as such. 
For this reason make sure that you recover bitcoin from your seed somewhere that is private and that has no cameras/CCTV. 
- Don't read your seed aloud as someone could hear it. 
- Don't type it into a computer

### What is the Derivation Path?

[StackExchange](https://bitcoin.stackexchange.com/questions/78993/default-derivation-paths)
	
### How often should I check backups?

You should definitely check your backup as part of your process for backing up. Provided that you have done this correctly there should be no need to actually sweep bitcoin from the backup unless you need the bitcoin. It is worth checking that the backup remains accessible at irregular intervals (say every 1-3 years). It is worth checking because if a single backup disappears you can recover using a secondary backup (if there is a chance that the backup was stolen) or make a replacement backup (if you are completely confident that the backup was just damaged, e.g. house fire). Don't regularly check backups (e.g. the 1st Jan each year) as this could be obvious and lead to people discovering your backup.

More reading on this subject: [SmartCustodyWhitePapers](https://github.com/BlockchainCommons/SmartCustodyWhitePapers/blob/master/%23SmartCustody-_Simple_Self-Custody_Cold_Storage_Scenario.md)
