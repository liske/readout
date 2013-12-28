readout
=======

about
-----

*readout* does text to speech convertion using Speech::Google:TTS of
Niels Dettenbach. It should be used for short texts supplied as
command line arguments.

*readout* does local caching, the Google stuff is only used for new
texts.

It could be used for home automation or monitoring stuff.


usage
-----

```bash
$ ./readout <first text block>[| <second text block> [| <third text block>] ...]
/home/thomas/.cache/readout/lang-en/tts_Us2s8Z.wav
/home/thomas/.cache/readout/lang-en/tts_lKj319.wav
/home/thomas/.cache/readout/lang-en/tts_IH_kBH.wav
...
```

Texts blocks can be splitted by pipes ('|'). Each block is written to a single
file. This can be used for caching.

For playback you might pipe it into *xargs* like this:

```bash
$ ./readout Hello World\! | xargs aplay
Playing WAVE '/home/thomas/.cache/readout/lang-en/tts_9c__3k.wav' : Signed 16 bit Little Endian, Rate 16000 Hz, Mono
```

The language is derived from the environment variable *LANG*. Languages can
be enforced by setting the *READOUT_LANG* environment variable.


install
-------

The following software is required:

* [Speech::Google::TTS](http://www.syndicat.com/open_source/google/perl/googletts/)
* mpg123
