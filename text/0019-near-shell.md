- Proposal Name: near-shell
- Start Date: 2020-02-03)
- NEP PR: [nearprotocol/neps#0000](https://github.com/nearprotocol/neps/pull/0000)
- Issue(s): link to relevant issues in relevant repos (not required).

# Summary
[summary]: #summary

NEAR Shell is one of the primary tools NEAR developers must use to develop and interact with NEAR networks and smart contracts.  Today, NEAR Shell contains the base commands for account creation and deletion, login, viewing account state and keys, sending tokens, creating staking transactions, and building, deploying, and calling smart contracts. There are more opportunities to integrate core NEAR features to expose them directly to users.  This proposal is to enhance NEAR Shell to represent all major functionality of NEAR.  For example, validator node management, network selection, native OS key management and integration, smart contract development (including testing, and interaction) could be added.  

NEAR Shell is an excellent tool to attract and engage new NEAR developers, both core and contract level, and if it contains all the required features to select and configure and deploy NEAR networks, nodes, crypto assets (i.e., keys), accounts, and wallets, it can be the ideal single-entry point for those potential new hackers.  

# Motivation
[motivation]: #motivation

These enhancements are intended to simplify and enhance developer and user productivity by providing a single command-line tool which exercises all major features of NEAR.  As each major piece of NEAR functionality is added to Near Shell, we should see utilization of each of those features increase.  Additionally, community mindshare and understanding of NEAR should increase as NEAR Shell will contain detailed help documentation for each major feature with clear examples of use, just like Linux man pages and/or other major CLI tools which have integrated help for each command.


# Guide-level explanation
[guide-level-explanation]: #guide-level-explanation

Using NEAR Shell, users can configure accounts, networks, and an instance of a server validator node on the host machine the shell is running.  An instance of NEAR Shell loads its state from the configuration directory and files stored in the default location:  `~/.near`.  Once the configuration is loaded, the active account and network are selected automatically either from the previously stored configuration or the defaults as shipped with NEAR Shell.

## NEAR Shell Top-Level Commands 

### `near network <command>`

This command category is used to select and configure NEAR networks for a NEAR Shell user.  This category manipulates the user's `~/.near` configuration to allow a user to specify NEAR network details via the CLI instead of manually editing config files.

Sub-commands for `network` might include:

* `near network list` : Display the current list of networks for the current instance of NEAR Shell.  
* `near network status` :  Show the user's current network configuration.
* `near network select` : Select a NEAR network as the default network for subsequent NEAR Shell commands as well as the network configuration for a local server validator node managed by this instance of NEAR Shell.
* `near network add` : Add a network to the users's `~/.near` config files.
* `near network remove` : Remove a network from tthe `~/.near` config files.
* `near network monitor` : Interactively monitor one or more NEAR networks in a curses-like interface updated in a specified interval, default of 1s.
* `near network help` : Display help on network subcommands. 

### `near account <command>`

This category is used to create, select, and configure accounts on NEAR networks for a given NEAR Shell user.  

* `near account list`   : Display list of accounts configured on local host.
* `near account status` : Display status of active or specified account.
* `near account create` : Create a new account or sub-account.
* `near account delete` : Delete an account or sub-account.
* `near account select` : Select an account from the list of locally configured accounts as the active account.
* `near account login`  : Log in the current active or specified account.
* `near account logout` : Log out the current active or specified account.
* `near account help`   : Display help on account subcommands.

### `server`

These commands are used to administer a NEAR server validator node.  Currently, only one server per NEAR Shell is proposed; however, multiple servers per physical host should be considered.

* `near server status`  : Display status of NEAR validator server on current host.
* `near server start`   : Start NEAR validator server on current host.
* `near server stop`    : Stop NEAR validator server on current host.
* `near server monitor` : Interactively display NEAR validator server status on current host.
* `near server tail`    : Tail the log of the NEAR validator server on current host.
* `near server help`    : Display help on server subcommands.

### `near tokens <command>`

* `near tokens send`	: Send tokens to another NEAR account.
* `near tokens status`	: Display tokens in wallet.
* `near tokens stake`
* `near tokens help`

### `near key <command>`

### `near contract <command>` 
* `near contract list`
* `near contract status`
* `near contract add`
* `near contract remove`
* `near contract build`
* `near contract deploy`
* `near contract call`

### `near config <command>`

For user-facing NEPs this section should focus on user stories.


# Reference-level explanation
[reference-level-explanation]: #reference-level-explanation

This is the technical portion of the NEP. Explain the design in sufficient detail that:

- Its interaction with other features is clear.
- It is reasonably clear how the feature would be implemented.
- Corner cases are dissected by example.

The section should return to the examples given in the previous section, and explain more fully how the detailed proposal makes those examples work.

# Drawbacks
[drawbacks]: #drawbacks

Why should we *not* do this?

# Rationale and alternatives
[rationale-and-alternatives]: #rationale-and-alternatives

- Why is this design the best in the space of possible designs?
- What other designs have been considered and what is the rationale for not choosing them?
- What is the impact of not doing this?

# Unresolved questions
[unresolved-questions]: #unresolved-questions

- What parts of the design do you expect to resolve through the NEP process before this gets merged?
- What parts of the design do you expect to resolve through the implementation of this feature before stabilization?
- What related issues do you consider out of scope for this NEP that could be addressed in the future independently of the solution that comes out of this NEP?

# Future possibilities
[future-possibilities]: #future-possibilities

Think about what the natural extension and evolution of your proposal would
be and how it would affect the project as a whole in a holistic
way. Try to use this section as a tool to more fully consider all possible
interactions with the project in your proposal.
Also consider how the this all fits into the roadmap for the project
and of the relevant sub-team.

This is also a good place to "dump ideas", if they are out of scope for the
NEP you are writing but otherwise related.

If you have tried and cannot think of any future possibilities,
you may simply state that you cannot think of anything.

Note that having something written down in the future-possibilities section
is not a reason to accept the current or a future NEP. Such notes should be
in the section on motivation or rationale in this or subsequent NEPs.
The section merely provides additional information.
