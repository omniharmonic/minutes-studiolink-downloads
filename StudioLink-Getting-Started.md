StudioLink — Getting Started
===========================

Host: Apple Silicon Mac, macOS 14 or later.
Guests: a current Safari or Chrome browser with camera/microphone access.

INSTALL
1. Open the StudioLink disk image and drag StudioLink to Applications.
2. Open StudioLink from Applications. Its dashboard opens in your browser.
3. Follow the device check. Do not start recording until everyone is ready.

FFmpeg and ffprobe are included. No Homebrew, Node.js or Go installation is
needed. The app and disk image are Developer ID signed and notarized when
built for release. Media tools' source, build instructions and licenses are
inside StudioLink.app → Show Package Contents → Contents → Resources.

CONNECT A REMOTE GUEST
1. Install Tailscale from https://tailscale.com/download on the host and guest
   devices. Each person signs into their own account.
2. On the host Mac, enable private HTTPS Serve for StudioLink. The dashboard's
   connection guide shows the command and validates the resulting address.
   This is private Serve, not public Funnel.
3. In Tailscale's admin console, share the host Mac with the guest. The guest
   accepts that machine share under their account and connects Tailscale.
4. The guest first opens the host's HTTPS server check. If Safari cannot find
   the server, enable Tailscale DNS on their device and MagicDNS on their
   account's tailnet, reconnect, and retry. A studio invitation cannot grant
   private-network access.
5. Copy a studio invitation from the dashboard. Send it to your guest. They
   check their devices and request admission; you approve them in the studio.
   Keep the local host dashboard private. Invitations contain session access;
   do not post them publicly.

RECORD AND EXPORT
Before joining, select the desired camera resolution and optionally enable
Uncompressed microphone track. The preview reports the negotiated resolution.
Record a short test, stop, and wait for each participant's upload receipt.
Keep the phone's Safari page foreground and its site data until receipt.
Process the take, then download its editor package. Preserve original media.
Import timeline.fcpxml in Resolve, relinking media to the package's media folder
when prompted. Camera angles and isolated microphones remain separately
editable. Resolve multicam import was tested; Final Cut/Premiere import still
needs independent verification. Review synchronization before important work.

YOUR DATA AND RUNNING HOST
Recordings and logs live in ~/Library/Application Support/StudioLink.
Closing the browser does not stop the host; it keeps uploads available.
Reopening the same app reuses its host. An old host on port 7443 is never
silently replaced: finish active sessions and stop it before updating.
The current launcher does not provide a menu-bar Quit Host control. For an
advanced/local stop, identify the StudioLink daemon in Activity Monitor and
quit it only after recording, uploads and exports have finished.

VALIDATION LIMITS
Separate-account iPhone joining/reconnection, Full HD video, isolated WAV
upload and Resolve multicam import passed. Short real-device checks and
synthetic two-minute drift tests do not guarantee hour-long synchronization.
Installation on an unrelated clean Mac remains to be checked.
