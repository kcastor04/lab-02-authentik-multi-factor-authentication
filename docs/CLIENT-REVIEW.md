# Client Review: Lab 02 Setting Up Multi-Factor Authentication

**Repository folder:** `lab-02-authentik-multi-factor-authentication`
**Status:** Client review (not published)
**Purpose:** Fourth lab package of the nine-lab portfolio, built in the same style and evidence approach as Labs 03, 07 and 06.

This file is for internal review only. It can be removed before publication.

**How to review:** open [`preview.html`](preview.html) in any web browser. No installation or internet connection is needed: images, styling and the diagram renderer are embedded. It is a local approximation of the README, not an exact GitHub rendering, and `README.md` remains the deliverable. Use *Expand all sections* at the top of the preview to open every collapsible section at once. The links to the diagram PNGs are relative, so keep the extracted folder structure intact (`docs/` next to `assets/`). Like this file, `preview.html` is a review aid and should be removed before publication.

---

## 1. Decisions required before publication

| # | Decision | Options / notes | Client answer |
|---|---|---|---|
| 1 | **Approve style and content** | Approve as is, or list changes (tone, length, section depth, badge set, heading emojis, diagram style). | |
| 2 | **Hands-on completion** | Did the portfolio owner personally complete the basic TOTP setup (Part 1)? | |
| 3 | **Optional scenarios completed** | Which, if any, of WebAuthn (requires HTTPS), conditional MFA by group and backup codes were actually completed? They are currently documented as not executed. | |
| 4 | **Own screenshots or results** | Do you have your own safe screenshots or notes (stage configuration, flow bindings, device lists, the code prompt with an empty field)? Anything shared will be reviewed before use and must not show QR codes, setup secrets, one-time codes, backup codes or passwords. | |
| 5 | **Permission to republish source material** | The lab text and the 25 selected screenshots come from *Hands-On IAM Labs – Lab 2: Setting Up Multi-Factor Authentication* (V11) by Andrew, All Things Identity. Please confirm you have permission to republish them publicly, or tell us to replace them with your own screenshots. | |
| 6 | **Accept screenshot exclusions** | 27 of the 52 figures are excluded, including all enrollment screens (2.20, 2.21, 2.22, 2.26), the backup-code screen (2.44), the populated code screen (2.29) and password screens (2.2, 2.17, 2.19). Reasons are in [`evidence-manifest.json`](evidence-manifest.json). Confirm, or name any figure you want reconsidered. | |
| 7 | **GitHub owner** | GitHub username or organization that will own the repository. | |
| 8 | **Repository name** | Proposed: `lab-02-authentik-multi-factor-authentication`. Confirm or provide an alternative. | |
| 9 | **Repository visibility** | Public or private. Nothing will be created or pushed until this is confirmed. | |

---

## 2. How the answers change the README

- **If hands-on completion is confirmed with your own evidence:** the evidence-scope note will move to execution-based wording, your safe screenshots can be added after review, and the status badge will change from *Client review* to a completion status.
- **If completion is confirmed without your own evidence:** the guide screenshots and attribution stay, and the wording can say the lab was completed while noting that screenshots are the guide's.
- **If optional scenarios were completed:** the relevant subsection will say so; WebAuthn can only be described as completed if it was done on an HTTPS instance.
- **If completion is not confirmed:** the current wording stays (source-described, source-illustrated or expected).
- **If republishing permission is not available:** guide screenshots will be removed and the README will rely on the configuration tables and the custom diagrams.

---

## 3. Unverified prerequisite and recovery details

Please confirm or correct:

- Lab 0 (Authentik instance) and Lab 1 (synced accounts without passwords) were completed before this lab.
- The Authentik version used, if different from the guide's 2026.8 (menus differ up to 2026.2).
- How the admin account is protected against losing its only authenticator in your environment (for example admin backup codes stored privately). The guide describes no break-glass or command-line recovery, and none has been added.
- Whether lost-device recovery (deleting a device and re-enrolling) was actually tested.

---

## 4. Evidence and safety decisions already applied

- All screenshots are attributed to All Things Identity and labelled as the guide author's examples. Exact source captions are kept in [`evidence-manifest.json`](evidence-manifest.json); README captions are summaries.
- **Every one of the 52 figures was inspected individually.** In the source, QR codes, codes, backup codes and IPs had already been replaced with placeholders by the author. Sensitive screen types were still excluded rather than redacted, so **no redaction was applied** and no original containing secrets is in the package.
- Selected screenshots were re-encoded, which removes PNG metadata.
- No passwords, QR codes, TOTP secrets, one-time codes, backup codes or server addresses are included; the README uses `YOUR_AUTHENTIK_URL`.
- The NIST SP 800-63B-4 statements are attributed to the guide and not presented as independently verified; no compliance claim is made.
- The basic TOTP-only configuration and the optional scenarios are kept separate throughout.
- **Editable diagrams:** the architecture and workflow diagrams are Mermaid diagrams written as text in `README.md`, with matching PNG exports in `assets/` linked below each diagram.
- **No LICENSE file** has been added; that needs confirmed instructions.

---

## 5. Unresolved source limitations

- **WebAuthn on HTTP.** The guide's lab runs on plain HTTP, where WebAuthn enrollment cannot complete. No WebAuthn result exists.
- **Conditional MFA result screenshot.** Figure 2.42 shows only a generic signed-in dashboard, so the member/non-member difference is source-described rather than illustrated; it is excluded.
- **Recovery depends on scope.** Deleting a device leads to re-enrollment only while the user is still subject to the force-configure validation stage.
- **Admin self-recovery.** An admin who loses their only factor cannot recover through the protected admin console; the guide's mitigation is admin backup codes.
- **No metrics or business scenario.** The guide gives no measurements and describes no specific organization, so none is reported.
