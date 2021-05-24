# Schnorr


There's a lot of good links here related to next steps.

Please especially look into

- [ ]  Schnorr
- [ ]  Adapter signatures
- [ ]  Pay to contract

Yeah it’s 
super interesting. Not much actually progress. But the direction seems 
quite promising. In a few weeks time we will talk overall architecture 
with Christopher. He has a ton of thoughts here.

On Thu, Mar 11, 2021 at 11:13 [chenpowei@bitmark.com](mailto:chenpowei@bitmark.com) <[chenpowei@bitmark.com](mailto:chenpowei@bitmark.com)> wrote:

> sure no problem.
      My research these days are on rgb, L2, L3, VM, PSBT, musig2,
      Descriptors, Gordian.
      rgb is very interesting. The content includes the realization of
      erc20, erc721, identification, and audit log on the Bitcoin L2 and
      L3 network.
      I will read it through the following content.
      It seems that rgb is still under development. I don't know how
      long it can be done. LOLSean Moss-Pultz 於 2021/3/11 上午10:15 寫道:
      
      Hi Po Wei
          There's a lot of good links here related to next steps. 
            Please especially look into- Schnorr - Adapter signatures- Pay to contractChristopher will circle back with you in about 2 weeks
              time. He's just overloaded now with releases. Best,Sean ---------- Forwarded
                message ---------
                From: Christopher
                  Allen <ChristopherA@lifewithalacrity.com>
                Date: Tue, Dec 3, 2019 at 5:01 AM
                Subject: Getting started with Schnorr?
                To: Marcelo Araujo <msa@bitmark.com>
                Cc: Sean Moss-Pultz <sean@bitmark.com>Marcelo,
                    We should schedule a call, but if you want to get
                    started here are my ideas for a flow.
                    The underlying library we want to use is https://github.com/BlockchainCommons/secp256k1-schnorrsig —
                    this is the library that implements x-only Schnorr
                    to the current BIP-Schnorr proposal. There are
                    currently no command-line utilities that use it.
                    Here is what I'm thinking about cli and build
                    environment. First off, we should be looking at C
                    and C++ as those can be used by both Android &
                    iOS. We want to be careful about the use of object
                    inheritance and hierarchies — bitcoin-core devs
                    minimize that. I've been told that bitcoin-core uses
                    C++ as there are more mature libraries for analyzing
                    the code. 
                    In general, most bitcoin-core projects use automake
                    and autoconf, and so does the secp library, we
                    should consider doing the same. 
                    I have run into problems in the past with how
                    libraries link to projects. Some people like using
                    git submodules and others like git subtrees. I lean
                    in security code to using submodules as it points to
                    a specific commit in another repository, which makes
                    security and auditing dependencies more clear. But
                    I'm reasonably open if you prefer subtrees.
                    Next we need to leverage a mature library for
                    handling CLI and standard i/o. I have heard good
                    things about https://github.com/muellan/clipp and https://github.com/CLIUtils/CLI11 
                    Though often the CLI tool should just output a
                    single value, I really like how bitcoind also allows
                    the option for parameterized input and JSON output.
                    See the chapter I wrote on JQ for my bitcoin on the
                    command line course https://github.com/ChristopherA/Learning-Bitcoin-from-the-Command-Line/blob/master/04_2__Interlude_Using_JQ.md.
                    Thus we may want to leverage a simple C++ JSON
                    library. I'm not sure if we should go as far as https://github.com/nlohmann/json but
                    something simpler like https://github.com/open-source-parsers/jsoncpp or
                    the header only https://github.com/taocpp/json. 
                    As https://github.com/CLIUtils/CLI11 and https://github.com/taocpp/json
                    are both header-only, if we want to go simpler they
                    may work well together.
                    The next step is to actually do our Schnorr
                    operations. Poelstra wrote a library that does some
                    useful ones at https://github.com/apoelstra/sighacker,
                    but he does it from his own hack of secp and it
                    doesn't work with x-only BIP-Schnorr. Initially
                    simple signing is the most important, but
                    signtocontract and some adaptor signature ideas are
                    the ultimate direction we want to move to. https://tokyo2018.scalingbitcoin.org/files/Day2/workshop-on-scriptless-scripts.pdf
                    The first thing I'd like to emulate is detached
                    signatures like minisign https://github.com/jedisct1/minisign but
                    with schnorr. It should be able to a minisign style
                    output or do a JSON output. I'm not quite sure if
                    (or how best) to do armored signatures, but suspect
                    that https://saltpack.org/
                    has some ideas. I've attached some other ideas from
                    Mark Friedenback on what this signing utility might
                    look like.
                    Longer term I'd like to puzzle how to leverage
                    encryption and some capabilities ideas. I like what
                    minilock https://45678.github.io/miniLock-file-format/2.html functionality
                    offers but I think it can be done both Schnorr musig
                    rather than only Schnorr singlesig, and I think
                    there are benefits for group signing of minilock
                    style files.
                    There are also some good ideas in did:git https://github.com/dhuseby/did-git-spec/blob/master/did-git-spec.md —
                    my thoughts are that fog-like encrypted data objects
                    are somewhat like git repos but are only valid if
                    the signatures of all the changes are valid. That is
                    how write/update/append capabilities might function
                    — they give you a musig signature that gives you the
                    authority to sign a commit.
                    Read through these and tell me what you think. P.S.
                    What is your Github account? 
                    — Christopher Allen
                    musign
                    ======
                    Musign is a simple tool to create multi-party
                    signatures for files, and to
                    verify those signatures, using the Schnorr signature
                    algorithm over the
                    secp256k1 elliptic curve.
                    Creating a simple (single-signer) key pair
                    ------------------------------------------
                    A new private key can be generated with the `genkey`
                    command:
                        $ musign genkey
                        Please enter the path in which to save the key
                    (~/.musign/default): <ENTER>
                        Please enter a password to protect the secret
                    key.
                        Password: <PASS>
                        Password (one more time): <PASS>
                        Deriving a key from the password in order to
                    encrypt the secret key... done
                        The secret key was saved as ~/.musign/default --
                    Keep it secret!
                        The public key was saved as
                    ~/.musign/default.pub -- This can be public.
                        Files signed using this key pair can be verified
                    with the following command:
                        musign verify --pubkey
                    mu1qar0srrr7xfkvy5l643lydnw9re59gtzzwf5mdq
                        $
                    The private key is encrypted with ChaCha20 as the
                    stream cipher, Poly1305 as the
                    MAC, and Argon2id as the key derivation function,
                    and stored in the file path
                    specified.
                    The public key is bech32-encoded and stored in the
                    same file path but with the
                    ".pub" extension.  It is also displayed on the final
                    line of the terminal
                    output.
                    Creating an aggregate verification pubkey
                    -----------------------------------------
                    Musign can use the properties of Schnorr signatures
                    to create combine multiple
                    distinct public keys into single verification key
                    which requires the cooperation
                    of all of the corresponding private key holders to
                    generate a valid signature.
                        $ musign combine -p KEY1 -p KEY2 [-p KEY3...]
                        Multiple public keys provided; calculating
                    aggregate verification key.
                        Files signed using this aggregate key can be
                    verified with the following command:
                        musign verify --pubkey
                    mu1qar0srrr7xfkvy5l643lydnw9re59gtzzwf5mdq
                        $
                    Signing a file with a single key
                    --------------------------------
                    Creating a signature requires specifying which
                    file(s) to sign, which key to
                    use, and where to store the resulting signature:
                        $ musign sign FILES... [-o sigpath.sig] ([-i
                    keypath] | [-s secret])
                        Password: <PASS>
                        Deriving a key from the password and decrypting
                    the secret key... done
                        Signature generated and saved to sigpath.sig
                        $
                    If no key is specified, `~/.musign/default` is used.
                    If a single file is specified, the output defaults
                    to signed file's path with
                    the ".sig" extension added.  If multiple files are
                    signed, specifying the output
                    path is required.
                    Musign uses SHA-512 to reduce the file(s) to be
                    signed to a compact message
                    value, which is then signed with the secret key over
                    the secp256k1 curve.
                    Creating a multi-key aggregate signature
                    ----------------------------------------
                    Musign is capable of using the MuSig signature
                    aggregation mechanism[MuSig] to
                    interactively construct a compact, efficient
                    aggregate signature.
                    Using multiple keys to generate a single, compact
                    signature is necessarily a
                    multi-step process for security reasons.  First each
                    signer commits to hash of
                    the public portion of a value they will use in their
                    signature.  Only once they
                    have seen a commitment from all the other signers is
                    it safe to reveal their own
                    preimage value, with knowledge of all preimages
                    being required to sign.
                        $ musign setup FILES [-f statepath] -p PUBKEY1
                    -p PUBKEY2...
                        Initialized signing plan and saved to
                    ./default.musign
                        Files signed using this aggregate key can be
                    verified with the following command:
                        musign verify --pubkey
                    mu1qar0srrr7xfkvy5l643lydnw9re59gtzzwf5mdq
                        $
                    All signing state is contained within the
                    `statepath` file, which defaults to
                    `default.musign`.  This file is provided to the
                    `sign` command for each step of
                    the signing process, during which it is updated with
                    whatever values the signer
                    can provide.
                        $ musign sign -f default.musign ([-i keypath] |
                    [-s secret])
                        (Output TBD)
                    With each invocation musign accomplishes whatever
                    steps of the multi-party
                    signing process that it can, then performs an
                    in-place update of the statefile.
                    The current state and required next steps of the
                    signing operation are reported
                    to the user on the command line.  The current
                    signing state can be queried from
                    the statefile at any time as well:
                        $ musign info -f default.musign
                        (Output TBD)
                    The statefile can either be passed around among the
                    signers in a serial fashion,
                    or it can be copied to each of the signers and
                    signed in parallel.  In the
                    latter case, the results need to be merged before
                    progress can continue:
                        $ musign combine FILES... -o default.musign
                        (Output TBD)
                    Once all signing steps have been accomplished, the
                    signature file is output by
                    the last invocation of `musig sign`.
                    Verifying a file signature
                    --------------------------
                    As the signatures for single-owner keys and
                    multi-key aggregates are
                    indistinguishable, a single command verifies both:
                        $ musign verify filename [-x sigpath] ([-i
                    keypath] | [-p pubkey])
                        filename: OK
                        $-- 
Chen Po Wei

Researcher

Bitmark restores trust in data. #digitalrights