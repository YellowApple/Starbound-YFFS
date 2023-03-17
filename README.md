# YFFS: YellowApple's Friendly Froggs and Shadows

No more senseless murder of friendly amphibians and ghosts.

# What is it?

It's a mod for [Starbound](https://playstarbound.com/) that prevents
players from accidentally murdering non-hostile Frogg and Shadow NPCs
in cold blood.

# Why'd you make it?

Because I got tired of my turrets - which I placed to *protect* the
innocent Froggs and Shadows - mowing them down instead.  I didn't see
any other mods doing this, so I did it myself.

# How do I install it?

Multiple ways:

- Download YFFS.pak from the Starbound forums (FIXME: actually upload
  it there and add a link here) and stick it in Starbound's mods
  folder (like any other mod)
- Subscribe to it on the [Steam
  Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=2947934849)
- Clone it into Starbound's `mods` folder:
  - On Linux: `git clone
    https://github.com/YellowApple/Starbound-YFFS.git
    ~/.steam/steam/steamapps/common/Starbound/mods/YFFS`
  - On other platforms: ¯\\\_(ツ)_/¯


# Will this work in multiplayer?

¯\\\_(ツ)_/¯

# Is this compatible with other mods?

As long as those mods don't depend on the Frogg and Shadow NPC types
having a damage team other than "friendly", then yes, this should be
fully compatible with them.

# Will this break my saves?

Highly unlikely.  It's just two JSON patches.  Uninstalling will
simply revert the damage teams to vanilla (returning them to being
vulnerable to damage by the player and/or the player's turrets).

# What are the known issues with it?

All known bugs are tracked on
[GitHub](https://github.com/YellowApple/YFFS/issues).

# I'm a modder.  How can I hack on it?

It's just an ordinary Starbound mod, so all the Lua files and such are
in their normal places.  Clone the repo, make your changes, submit a
PR, all that jazz :)

I use GNU Make (BSD Make might work too?) to automate packaging for
the Steam Workshop (using
[SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD); running
`make` in the mod's directory will generate `out/pkg/contents.pak`,
and running `make upload` will generate a valid `manifest.vdf` and
handle the uploading.  Obviously you need permissions in order to
actually upload over the top of my version; if you're publishing your
own fork, change the `"publishedfileid"` field in
`metadata.vdf.template` to `"0"` to tell SteamCMD to create a new
Workshop item instead of attempting to overwrite mine (and don't
forget to change that to whatever gets set in the generated
`manifest.vdf`!).

Note that you need the `STEAMCMD_USER` environment variable set for
`make upload` to work; I use [`asdf` and
`direnv`](https://github.com/asdf-community/asdf-direnv) to
automatically set `STEAMCMD_USER` to my Steam username whenever I `cd`
into YEET's mod folder; you can do the same by copying `.envrc.sample`
to `.envrc`, adjusting to use your Steam username (whichever one you
use to log into Steam itself), and running `direnv allow` to activate
it.
