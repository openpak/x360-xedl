# Protocol: x360-xedl

Live service 11 (`xedl`), XAM 17559.

See the layout comment in `internal/xedl/xedl.go` (big-endian, UTF-16BE strings). Without service 11 in D7
the Account Recovery applet quits with "problem with the credentials" (800704DB).
