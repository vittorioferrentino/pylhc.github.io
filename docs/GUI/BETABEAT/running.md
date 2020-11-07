# Running the Beta-Beat GUI

The GUI can be started from inside eclipse (which will prompt you with the logging window) or from an [external archive site][archive]{target=_blank}.
At the following links, you can also find:

- The current [production version][prod_gui]{target=_blank}.
- The current [development version][dev_gui]{target=_blank}.
- The complete [list of releases][releases]{target=_blank}.

??? note
    Please note that these site are currently available only to devices connected to the CERN network.

From there, open the `.jnlp` executable inside a browser, or call it with `javaws` from the command line.
For convenience, there are scripts to run it directly from `afs` at the following location:
```bash
/afs/cern.ch/eng/sl/lintrack/Beta-Beat.src/GUI
```

!!! info "Compatibility Issues"
    Since `javaws` (java web start) makes trouble due to intenal security mechanisms, a replacement named `jws` was developed and has to be used to run the `jlnp` file.
    For further information see the [jws Confluence][jws_confluence]{target=_blank} page.

## Requirements

The following are required to run the `Beta-Beat` GUI:

- A Linux-based operating system (running CentOS 7 as do the CERN servers is recommended).
- A version of `Java>=7`.
- The [`jws`][jws] replacement for `javaws`.

!!! info
    Being inside of the Technical Network is required for the KnobPanel.
    To do so, `ssh` into one of the hosts, for instance `cs-ccr-dev<number>.cern.ch`.

## Troubleshooting

You may encounter the following errors:

#### Problems with execution due to disabled Java

If you encounter a complaint about `Java` being too old, try using `/mcr/bin/javaws`.

!!! failure
    ```bash
    javaws http://abwww/ap/dist/lhc/lhc-app-beta-beating/PRO/BetaBeating-Control-3t.jnlp
    ```
    **Disabling Java as it is too old and likely to be insecure. To reenable use jcontrol utility**

!!! success
    ```bash
    /mcr/bin/javaws http://abwww/ap/dist/lhc/lhc-app-beta-beating/PRO/BetaBeating-Control-3t.jnlp
    ```

#### Unspecific Error

!!! failure
    Any random error

If so, check that you can import `numpy` from the `omc-anaconda-python`.
If this leads to the previously raised error, then the permissions are broken.
Either fix the permissions on `afs` or ask someone to do so for you.

[archive]: http://abwww.cern.ch/ap/
[prod_gui]: http://abwww.cern.ch/ap/pro/lhc/lhc-app-beta-beating/BetaBeating-Control-3t.jnlp
[dev_gui]: http://abwww.cern.ch/ap/next/lhc/lhc-app-beta-beating/BetaBeating-Control-3t.jnlp
[releases]: https://abwww.cern.ch/ap/dist/lhc/lhc-app-beta-beating/
[jws_confluence]: https://wikis.cern.ch/display/DVTLS/jws+-+a+replacement+for+javaws
[jws]: https://wikis.cern.ch/display/DVTLS/jws+-+a+replacement+for+javaws