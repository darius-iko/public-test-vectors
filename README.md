# Axinom DASH test vectors

This document lists the test vectors that Axinom offers for customers, partners and the general public.

This is the conservative branch of the test vectors, intended to showcase highly compatible but not very modern data. Only use this branch if you do not wish to target the most modern features of industry standards.

# Usage of Axinom DRM

All test vectors can be played back using both the PlayReady and Widevine DRM technologies for decryption.

PlayReady license server URL: http://drm-playready-licensing.axtest.net/AcquireLicense

Widevine license server URL: http://drm-widevine-licensing.axtest.net/AcquireLicense

The license server will provide nonpersistent licenses for the relevant keys upon each license request. To receive a license, you must add the HTTP header `X-AxDRM-Message` to the license request, with the value being a constant unique to each test vector. Example of license request:

    POST http://drm-widevine-licensing.axtest.net/AcquireLicense HTTP/1.1
    Host: drm-widevine-licensing.axtest.net
    X-AxDRM-Message: eyJ0eX...

# HTTPS compatibility notice

All URLs in this document are also accessible over HTTPS.

# v6.1-MultiDRM

A single-period multi-DRM presentation with all video and audio representations encrypted using the same key.

[4K manifest](http://media.axprod.net/TestVectors/v6.1-MultiDRM/Manifest.mpd)

[1080p manifest](http://media.axprod.net/TestVectors/v6.1-MultiDRM/Manifest_1080p.mpd)

[Download presentation](http://media.axprod.net/TestVectors/v6.1-MultiDRM.7z)

Adaptation set | Parameters
:--------------|:----------
Video          | 7x H264, up to 4K resolution at 6 Mbps
Audio          | 3x AAC-LC at 128 kbps
Text           | 5x WebVTT (segmented)

The content is encrypted according to CENC and contains PlayReady and Widevine metadata in both the manifest and the initialization segments, with the metadata in both locations being equivalent.

Adaptation set | Key ID                               | Content key
:--------------|:-------------------------------------|:------------------------
Video          | 6e5a1d26-2757-47d7-8046-eaa5d1d34b5a | GX8m9XLIZNIzizrl0RTqnA==
Audio (all)    | 6e5a1d26-2757-47d7-8046-eaa5d1d34b5a | GX8m9XLIZNIzizrl0RTqnA==

Value to use for X-AxDRM-Message header: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ2ZXJzaW9uIjoxLCJjb21fa2V5X2lkIjoiNjllNTQwODgtZTllMC00NTMwLThjMWEtMWViNmRjZDBkMTRlIiwibWVzc2FnZSI6eyJ0eXBlIjoiZW50aXRsZW1lbnRfbWVzc2FnZSIsImtleXMiOlt7ImlkIjoiNmU1YTFkMjYtMjc1Ny00N2Q3LTgwNDYtZWFhNWQxZDM0YjVhIn1dfX0.yF7PflOPv9qHnu3ZWJNZ12jgkqTabmwXbDWk_47tLNE`

# v6.1-MultiDRM-MultiKey

A single-period multi-DRM presentation with all video and audio representations encrypted, using a different key for every adaptation set.

[4K manifest](http://media.axprod.net/TestVectors/v6.1-MultiDRM-MultiKey/Manifest.mpd)

[1080p manifest](http://media.axprod.net/TestVectors/v6.1-MultiDRM-MultiKey/Manifest_1080p.mpd)

[Download presentation](http://media.axprod.net/TestVectors/v6.1-MultiDRM-MultiKey.7z)

Content type | Parameters
-------------|-----------
Video        | 7x H264, up to 4K resolution at 6 Mbps
Audio        | 3x AAC-LC at 128 kbps
Text         | 5x WebVTT (segmented)

The content is encrypted according to CENC and contains PlayReady and Widevine metadata in both the manifest and the initialization segments, with the metadata in both locations being equivalent.

Adaptation set | Key ID                               | Content key
:--------------|:-------------------------------------|:------------------------
Video          | 1530d3a0-6904-446a-91a1-33a115aa8c41 | ubafkhpLoQF0nyvzzouLpg==
Audio (en)     | c83eb639-e664-43f8-ae98-4039b0c13b2d | f5p7XvhuXKve9gx/v2pUsg==
Audio (en-AU)  | 3d8cc762-27ac-400f-989f-8ab5dc7d7775 | cRc6/royDmsPA3zKGkQ81w==
Audio (en-ET)  | bd8dad58-032d-4c25-89fa-c7b710e82ac2 | gDfgWVfz6O0Kq0+ZAV1miw==

Value to use for X-AxDRM-Message header: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ2ZXJzaW9uIjoxLCJjb21fa2V5X2lkIjoiNjllNTQwODgtZTllMC00NTMwLThjMWEtMWViNmRjZDBkMTRlIiwibWVzc2FnZSI6eyJ0eXBlIjoiZW50aXRsZW1lbnRfbWVzc2FnZSIsImtleXMiOlt7ImlkIjoiMTUzMGQzYTAtNjkwNC00NDZhLTkxYTEtMzNhMTE1YWE4YzQxIn0seyJpZCI6ImM4M2ViNjM5LWU2NjQtNDNmOC1hZTk4LTQwMzliMGMxM2IyZCJ9LHsiaWQiOiIzZDhjYzc2Mi0yN2FjLTQwMGYtOTg5Zi04YWI1ZGM3ZDc3NzUifSx7ImlkIjoiYmQ4ZGFkNTgtMDMyZC00YzI1LTg5ZmEtYzdiNzEwZTgyYWMyIn1dfX0.9t18lFmZFVHMzpoZxYDyqOS0Bk_evGhTBw_F2JnAK2k`

# v6.1-MultiDRM-MultiKey-MultiPeriod

A multi-period multi-DRM presentation with all video and audio representations encrypted, using a different key for every adaptation set and changing the encryption parameters for the different periods.

The two periods are simply the same audiovisual content presented twice in succession while varying some of the encryption parameters between the periods.

[4K manifest](http://media.axprod.net/TestVectors/v6.1-MultiDRM-MultiKey-MultiPeriod/Manifest.mpd)

[1080p manifest](http://media.axprod.net/TestVectors/v6.1-MultiDRM-MultiKey-MultiPeriod/Manifest_1080p.mpd)

[Download presentation](http://media.axprod.net/TestVectors/v6.1-MultiDRM-MultiKey-MultiPeriod.7z)

Content type | Parameters
-------------|-----------
Video        | 7x H264, up to 4K resolution at 6 Mbps
Audio        | 3x AAC-LC at 128 kbps
Text         | 5x WebVTT (segmented)

The content is encrypted according to CENC and contains PlayReady and Widevine metadata in both the manifest and the initialization segments, with the metadata in both locations being equivalent.

## Period 1

Adaptation set | Key ID                               | Content key
:--------------|:-------------------------------------|:------------------------
Video          | 53be7757-7288-4b6b-b20a-f05b64a4ef79 | /34ZeGgb0eDY4M7FD12vcg==
Audio (en)     | 0ed821a8-80ed-40ac-a804-927c9fdadbe9 | /6zlZEjHG0Ov698JfdL7aA==
Audio (en-AU)  | -                                    | -
Audio (en-ET)  | e47d78ca-94dc-45fb-9e3d-2a773aef74b2 | 3ZTeftObJfIHZeDvHAbarw==

## Period 2

Adaptation set | Key ID                               | Content key
:--------------|:-------------------------------------|:------------------------
Video          | 32a141e9-23ab-44ff-a6c7-5349c89451cf | qtC6/ovJfAVxoQDFLh5knQ==
Audio (en)     | -                                    | -
Audio (en-AU)  | 8d091966-44b5-4cf8-8a45-ed12fdb18d35 | Da70PZt6XWYOdNDcJdqCBw==
Audio (en-ET)  | e47d78ca-94dc-45fb-9e3d-2a773aef74b2 | 3ZTeftObJfIHZeDvHAbarw==

Value to use for X-AxDRM-Message header: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ2ZXJzaW9uIjoxLCJjb21fa2V5X2lkIjoiNjllNTQwODgtZTllMC00NTMwLThjMWEtMWViNmRjZDBkMTRlIiwibWVzc2FnZSI6eyJ0eXBlIjoiZW50aXRsZW1lbnRfbWVzc2FnZSIsImtleXMiOlt7ImlkIjoiNTNiZTc3NTctNzI4OC00YjZiLWIyMGEtZjA1YjY0YTRlZjc5In0seyJpZCI6IjBlZDgyMWE4LTgwZWQtNDBhYy1hODA0LTkyN2M5ZmRhZGJlOSJ9LHsiaWQiOiJlNDdkNzhjYS05NGRjLTQ1ZmItOWUzZC0yYTc3M2FlZjc0YjIifSx7ImlkIjoiMzJhMTQxZTktMjNhYi00NGZmLWE2YzctNTM0OWM4OTQ1MWNmIn0seyJpZCI6IjhkMDkxOTY2LTQ0YjUtNGNmOC04YTQ1LWVkMTJmZGIxOGQzNSJ9XX19.9YSK6QsDr4SYR7Q74ftq9mVtsT0ZkP3STE0zI-3mVIA`

# v6.1-Clear

This is a clear (no encryption) variant of the v6.1-MultiDRM-* presentations, to provide some comparison capability for diagnostics and debugging. The media data inside is equal to the variants that make use of DRM.

[Single-period 4K manifest](http://media.axprod.net/TestVectors/v6.1-Clear/Manifest.mpd)

[Single-period 1080p manifest](http://media.axprod.net/TestVectors/v6.1-Clear/Manifest_1080p.mpd)

[Multi-period 4K manifest](http://media.axprod.net/TestVectors/v6.1-Clear/MultiPeriod_Manifest.mpd)

[Multi-period 1080p manifest](http://media.axprod.net/TestVectors/v6.1-Clear/MultiPeriod_Manifest_1080p.mpd)

[Download presentation](http://media.axprod.net/TestVectors/v6.1-Clear.7z)

Adaptation set | Parameters
:--------------|:----------
Video          | 7x H264, up to 4K resolution at 6 Mbps
Audio          | 3x AAC-LC at 128 kbps
Text           | 5x WebVTT (segmented)

# Credits

Original content "Tears of Steel" by [Blender Foundation](http://mango.blender.org).

# Disclaimer

Axinom does not guarantee the continued availability of the test vectors or the license server nor the accuracy of any descriptive metadata.