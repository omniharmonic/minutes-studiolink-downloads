# Minutes & StudioLink

Signed Mac preview downloads from OmniHarmonic. Application source repositories remain private. This repository contains installers, setup guides and release notes; it does not contain user recordings, credentials or voice profiles.

| App | Download | Requirements |
| --- | --- | --- |
| **Minutes** | [Mac preview build 40](https://github.com/omniharmonic/minutes-studiolink-downloads/releases/tag/minutes-v1.0.0-preview.40) | Apple Silicon, macOS 15+; supported Apple on-device Speech language |
| **StudioLink** | [Mac host preview](https://github.com/omniharmonic/minutes-studiolink-downloads/releases/tag/studiolink-v1.0.0-preview.1) | Apple Silicon, macOS 14+; Tailscale for remote guests |

Both Mac applications are Developer ID signed and notarized by Apple. These are previews, not promises of complete SaaS parity. An unrelated clean-Mac installation and long-session hardware acceptance remain outstanding. Check the release's SHA256SUMS.txt if verifying your download.

## Minutes

Unzip the download, drag Minutes.app to Applications and open it. Install local speaker models in Settings → On-device speech, then approve Microphone and Speech Recognition when you choose to record. Mac audio capture also needs Screen & System Audio Recording permission. Audio remains on the device unless you explicitly configure an export.

Record or import a meeting, then review its transcript, summary and People. In People, listen to a sample and confirm the speaker. Remembering a voice is optional and requires consent plus at least 20 seconds of compatible usable speech. Strong matches can fill names in later recordings, but remain correctable. Calendar invitations provide context, not proof of attendance. Voice profiles currently remain separate on each device; they do not sync through Prism.

**Calendar preview limitation:** new Mac installations should use Apple Calendar. Owner-device Google sign-in has passed, but the Desktop Google registration is not provisioned in this public download, and wider Google audience/verification setup is incomplete. No owner's Google registration or account tokens are shipped. Existing configured installations retain their Keychain configuration.

The iPhone app is currently a paired-device development build. A universally installable IPA is not provided here; public iPhone distribution still requires TestFlight/App Store setup and review.

## StudioLink

Open the disk image and drag StudioLink to Applications. Open the app to launch its browser dashboard. FFmpeg and ffprobe are included; no Homebrew/Node.js/Go installation is needed.

For remote sessions, install/connect Tailscale on host and guest devices, enable private HTTPS Serve on the host using the dashboard guide, and share the host machine with a guest's Tailscale account. After that, send the separate StudioLink studio invitation and admit the guest. Network access and studio admission are separate. No public Funnel is required.

[Full StudioLink getting-started guide](StudioLink-Getting-Started.md).

## Privacy and third-party components

Minutes processes locally; explicitly selected exports send content to their configured destination. StudioLink records source media in each participant's browser and uploads it to the host. Tailscale connectivity and identity are managed through Tailscale. Keep original browser data until upload receipt.

FFmpeg's corresponding source, authenticated build instructions and LGPL notices are bundled inside StudioLink.app → Contents → Resources. Go module/runtime copyright notices are bundled there too. Minutes includes its third-party notices in application resources. Their licenses remain applicable.

Report reproducible issues here without posting meeting audio, transcripts, invitation links, credentials or voice-profile data. Describe app version, device/OS, steps and sanitized error wording.
