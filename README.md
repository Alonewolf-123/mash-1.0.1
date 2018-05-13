Mash Core 
===================================

[![Build Status](https://travis-ci.org/mash/mash.svg?branch=master)](https://travis-ci.org/mash/mash)

https://mashcoin.info

What is Mash?
--------------

Mash is an experimental new digital currency that enables instant payments to
anyone, anywhere in the world. Mash uses peer-to-peer technology to operate
with no central authority: managing transactions and issuing money are carried
out collectively by the network. Mash Core is the name of open source
software which enables the use of this currency.

Our vision is to make a steady passive income for our investors which are sustainable over the long term.
We will use the advantages of latest technologies in the area of machine learning, data and math analysis, artificial intelligence, blockchain and mobile development in order to bring to life a fully
autonomous clever trading bot.

For more information, as well as an immediately useable, binary version of
the Mash Core software, see https://mashcoin.info

License
-------

Mash Core is released under the terms of the MIT license. See [COPYING](COPYING) for more
information or see http://opensource.org/licenses/MIT.

Coin Specification
-------------------

Coin Specifications

Name:   MASH

Ticker:    MSH

Type:   POS and Pow/Masternode

Max supply:  210.000.000

Pre mine:  840.000

Algorithm:  x11

Block TIme: 1 Minute

Collateral: 10000 MASH

POW - 1 block Pre-mine = 0.4% = 840,000 coins

Early investor, Bounties, airdrop, pre-sale, future development

POW - 200 blocks POW ENDS -   1

POW - end

POS + MN Starts 

201- 4500 blocks   -   5 

4501-8500 blocks   -   20 

8501- 21000 blocks   -   25 

after 21001 blocks   -   30


Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test on short notice. Please be patient and help out by testing
other people's pull requests, and remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write unit tests for new code, and to
submit new unit tests for old code. Unit tests can be compiled and run (assuming they weren't disabled in configure) with: `make check`

Every pull request is built for both Windows and Linux on a dedicated server,
and unit and sanity tests are automatically run. The binaries produced may be
used for manual QA testing — a link to them will appear in a comment on the
pull request posted by [MashPullTester](https://github.com/MashPullTester). See https://github.com/TheBlueMatt/test-scripts
for the build/test scripts.

### Manual Quality Assurance (QA) Testing

Large changes should have a test plan, and should be tested by somebody other
than the developer who wrote the code.
See https://github.com/mash/QA/ for how to create a test plan.

Translations
------------

Changes to translations as well as new translations can be submitted to
[Mash Core's Transifex page](https://www.transifex.com/projects/p/mash/).

Translations are periodically pulled from Transifex and merged into the git repository. See the
[translation process](doc/translation_process.md) for details on how this works.

**Important**: We do not accept translation changes as GitHub pull requests because the next
pull from Transifex would automatically overwrite them again.

Translators should also subscribe to the [mailing list](https://groups.google.com/forum/#!forum/mash-translators).

Development tips and tricks
---------------------------

**compiling for debugging**

Run configure with the --enable-debug option, then make. Or run configure with
CXXFLAGS="-g -ggdb -O0" or whatever debug flags you need.

**debug.log**

If the code is behaving strangely, take a look in the debug.log file in the data directory;
error and debugging messages are written there.

The -debug=... command-line option controls debugging; running with just -debug will turn
on all categories (and give you a very large debug.log file).

The Qt code routes qDebug() output to debug.log under category "qt": run with -debug=qt
to see it.

**testnet and regtest modes**

Run with the -testnet option to run with "play mashs" on the test network, if you
are testing multi-machine code that needs to operate across the internet.

If you are testing something that can run on one machine, run with the -regtest option.
In regression test mode, blocks can be created on-demand; see qa/rpc-tests/ for tests
that run in -regtest mode.

**DEBUG_LOCKORDER**

Mash Core is a multithreaded application, and deadlocks or other multithreading bugs
can be very difficult to track down. Compiling with -DDEBUG_LOCKORDER (configure
CXXFLAGS="-DDEBUG_LOCKORDER -g") inserts run-time checks to keep track of which locks
are held, and adds warnings to the debug.log file if inconsistencies are detected.
