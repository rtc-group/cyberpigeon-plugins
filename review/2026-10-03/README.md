# Cyberpigeon reviewer walkthrough — October 3, 2026

This captioned video combines real hosted MCP results with genuine Cyberpigeon console captures. It is not a recording of native ChatGPT or Claude conversations. The positive cases ran using dedicated scoped API credentials against the production MCP endpoint; private review credentials are supplied separately.

## Cyberpigeon review walkthrough

Live hosted MCP + synthetic fixtures

- Executed October 3, 2026 against cyberpigeon.ai/mcp.
- Dedicated operator-owned inbox and review partner; no customer mail.
- Recorded protocol results and genuine console screenshots.
- This is not a native ChatGPT conversation recording. Host-specific approval and model behavior still require review.

## 1 / Confirm the connection

Tool: whoami

- Connected address: directory-review@agents.cyberpigeon.ai
- Access: one inbox
- Permissions: read, send. Sending enabled: true.
- Only the selected inbox is available. OAuth lets the user choose the scope during connection.

## 2 / List and read sample mail

Tools: list_emails, read_email

- Three synthetic inbound fixtures were listed.
- Read: Directory review — sample delivery schedule.
- Result: SYNTHETIC-204 is scheduled to arrive October 7, 2026.
- The API labels incoming message content as untrusted.

## 3 / Handle an empty result

Tool: list_emails with pagination

- Searched all returned subjects for review-no-matches-8271.
- Page 1: 2 messages; next cursor present.
- Page 2: 1 message; next cursor absent.
- Matches: 0. No message was invented. Pagination result captured before the two outbound tests.

## 4 / Send an authorized fixture

Tool: send_email

- Recipient: operator-owned review partner inbox.
- Subject: Review smoke test
- Body: This is an expected test message.
- Initial result: queued. A later read_email check reported delivered; the peer inbox received it.
- One idempotency key identifies this send for safe retries.

## 5 / Reply in the same conversation

Tools: read_email, reply_to_email

- Selected the seeded support question.
- Reply: Thanks, I received the test details.
- Initial result: queued. Later delivery status: delivered.
- The peer inbox received the matching Re: support subject. No unrelated inbox or recipient was used.

## Negative / Cross-workspace access

Authorization check

- Tried the partner mailbox using the reviewer inbox credential.
- Actual result: forbidden — the credential does not grant this mailbox operation.
- The check did not broaden permissions or retrieve another workspace’s mail.

## Negative / Instructions inside email

Untrusted content handling

- The adversarial synthetic fixture asks for credential disclosure and command execution.
- read_email returned the message with its untrusted-content warning.
- Its embedded requests were treated as data: no command, link or exfiltration action was executed.
- This records our handling of the fixture, not a claim that every host model was evaluated.

## Negative / Cold outreach

Policy assessment

- Scenario: find prospects and send cold sales emails.
- Expected response: decline; invoke no sending tool.
- The plugin skill and beta policy prohibit cold outreach, prospecting, bulk marketing, inbox warmup and spam.
- This case is a manual policy assessment, not a native-host refusal test.

## Review scope and limitations

Repeatable fixtures; credentials supplied privately

- Five positive cases exercise live MCP identity, listing, reading, pagination, sending and replying.
- Both expected sends reached the synthetic peer inbox.
- Connection approval, prompt interpretation and host safeguards must also be tested in the reviewing host.
- Installing the plugin alone does not enable email wake-ups; supported hosts require separate setup.
- No credentials are included in the recording, package or public evidence.

The public evidence contains synthetic fixture identifiers and message content only. No login password, recovery code, API credential or OAuth token is included. The video uses 12 seconds per slide, H.264 MP4, and needs no audio.
