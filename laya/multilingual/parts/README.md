# Split model.safetensors

`model.safetensors` (multilingual, 644 MB) is split into <=90 MiB parts to fit GitHub's 100 MB file limit.

Recombine (run inside this `parts/` folder):

    # bash / Git Bash / macOS / Linux
    cat model.safetensors.part-* > model.safetensors
    sha256sum -c SHA256SUM

    :: Windows cmd
    copy /b model.safetensors.part-00+model.safetensors.part-01+model.safetensors.part-02+model.safetensors.part-03+model.safetensors.part-04+model.safetensors.part-05+model.safetensors.part-06 model.safetensors
    certutil -hashfile model.safetensors SHA256

Expected SHA-256: 9d628fd971b700382ac6f65920a86f149777b2e748e0c955fb3b19695aa8f204

Then move `model.safetensors` up one folder into `multilingual/`.
