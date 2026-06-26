# UMI-Data-process

Uploaded artifacts:
- `openvins_ws-source.zip`
- `orbslam3_ws-source.zip.part01`
- `orbslam3_ws-source.zip.part02`
- `orbslam3_ws-source.zip.part03`

Notes:
- `openvins_ws` is provided as a single zip archive.
- `orbslam3_ws` is split into 3 parts for reliable upload.

Rebuild `orbslam3_ws-source.zip` on Windows PowerShell:

```powershell
$parts = @(
  'orbslam3_ws-source.zip.part01',
  'orbslam3_ws-source.zip.part02',
  'orbslam3_ws-source.zip.part03'
)
$out = [System.IO.File]::Create('orbslam3_ws-source.zip')
try {
  foreach ($p in $parts) {
    $bytes = [System.IO.File]::ReadAllBytes($p)
    $out.Write($bytes, 0, $bytes.Length)
  }
} finally {
  $out.Dispose()
}
```

Then extract:
- `openvins_ws-source.zip`
- `orbslam3_ws-source.zip`