# FiSH Module for ZNC

[ZNC Fish Wiki](http://en.znc.in/wiki/Fish)

Orig. Module: [fish.cpp](http://znc-msvc.googlecode.com/svn/trunk/flakes/fish.cpp)

## Install

### Building

    $ znc-buildmod fish.cpp

### Install

    $ cp fish.so ~/.znc/modules/

Tell ZNC to load the module:

    /msg *status loadmod fish
    /msg *fish Help

## Usage

    /msg *fish SetKey #secretChannel mySuperSecretKey

To disable encryption for a single message, prefix the message with `-e`

    /msg #secretChannel -e this won't be encrypted

Decrypted messages are prefixed with a blue `(e)`

If the module expected an encrypted message but received a unecrypted message it will prefix with a red `(d)`

To change the prefixes:

    /msg *fish SetConfig prefix_encrypted (+)
    /msg *fish SetConfig prefix_decrypted (-)

## Commands

* `Help`

* `SetKey <target> <key>`

  Sets `<target>`'s FiSH encryption key

* `DelKey <target>`

  Removes `<target>`'s FiSH encryption key

* `ShowKey <target>`

  Show the encryption key of `<target>`, if it has one set

* `ListKeys`

  Print out all of our keys

* `SetConfig <name> <value>`

  Set config option `<name>` to `<value>`

* `ListConfig`

  Print out all of our config options

* `KeyX <target>`

  Start a key exchange with `<target>`

## Configurables

* `prefix_encrypted`

  Default: (blue) `^12(e)^`

* `prefix_decrypted`

  Default: (red) `^4(d)^`
