# dx-3dHome-files

Static asset host for the WeChat GLB viewer mini-program. Served via jsDelivr.

## Layout

```
labubu_mobile_chunks.json        # manifest: byteLength, chunks[], chunkChars
labubu_mobile_chunks/            # base64-encoded GLB chunks (262144 chars each)
  labubu_mobile_color_000.txt
  ...
  labubu_mobile_color_072.txt
```

## URL pattern

Pin to a commit SHA so updates never invalidate the CDN cache mid-flight:

```
https://gcore.jsdelivr.net/gh/Datian1993/dx-3dHome-files@<commit-sha>/labubu_mobile_chunks.json
```

The mini-program (`utils/models.js`) holds the `chunkManifestUrl`. Update the
SHA in that file when publishing a new model build.
