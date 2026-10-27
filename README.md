# Sounding

Sounding is a Windows desktop app that reads your git repositories without ever changing them: history, the changes in
each commit, uncommitted work, files, findings, metrics and a measure of how complex the code is. Lumi, the assistant
on the right, answers questions about the repository you have open.

This repository holds **releases only**: the installers, nothing else. Download the latest one from
[Releases](../../releases/latest).

## Install

1. Download `Sounding_<version>_windows_x64-setup.exe` and its `.sha256` file from the release.
2. Check the file: in PowerShell, `Get-FileHash .\Sounding_<version>_windows_x64-setup.exe -Algorithm SHA256` must match the
   `.sha256` file.
3. Run it. It installs for your user and needs WebView2, which Windows 11 includes.

The build is **not code-signed**, so Windows SmartScreen may warn you; the checksum is how you confirm the file. A
portable ZIP with just `sounding.exe` is attached to each release too.

## Notes

- Your repositories are only read. What a scan reads is kept in a local index under `%LOCALAPPDATA%\Sounding`.
- Lumi sends your question and a summary of the open repository (never file contents) to the Innovacc AI platform, and
  needs a platform key saved in the Windows Credential Manager. Everything else works offline.
- Windows x64 only for now.
