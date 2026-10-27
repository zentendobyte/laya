# Split model.safetensors

`model.safetensors` (root laya, 843 MB) is split into 9 parts (<=90 MiB each) to fit GitHub's 100 MB file limit.

Recombine (run inside this `parts/` folder):

    # bash / Git Bash / macOS / Linux
    cat model.safetensors.part-* > model.safetensors
    sha256sum -c SHA256SUM

    :: Windows cmd (list parts 00 through 08 in order)
    copy /b model.safetensors.part-00+model.safetensors.part-01+...+model.safetensors.part-08 model.safetensors
    certutil -hashfile model.safetensors SHA256

Expected SHA-256: 891102d372688fc2a094dac56a384bc537b87c63f21f9f3dac0be2b7cbc8d86c

Then move `model.safetensors` up one folder into `laya/`.
