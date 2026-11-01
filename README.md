# flubi-radio-auth

Static OAuth redirect page for the flubi radio QR-code login.

Spotify only accepts HTTPS redirect URIs (except `127.0.0.1`). After login, Spotify sends the phone to
`https://mitea1.github.io/flubi-radio-auth/callback.html`; the page forwards `code` and `state` to the radio
on the local network (address encoded in `state`, private-network addresses only).

The authorization code is useless on its own: the PKCE verifier needed to redeem it never leaves the radio.
Source of truth: `docs/auth/callback.html` in the (private) flubi_radio repository.
