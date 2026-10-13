# PermitOps for Claude

![PermitOps](assets/icon.png)

Find job evidence with source links and page citations, and save explicitly
reviewed source excerpts privately into PermitOps. Published by Vanity Labs LLC.
The plugin files are free to use under the [free-use license](LICENSE).
Redistribution is restricted. PermitOps service subscriptions are separate.

## Download and install

Download **permitops-claude-0.3.0.zip** from the
[latest release](https://github.com/Vanity-Labs-1/permitops-claude/releases/latest).
In Claude web, Desktop, or Cowork, open **Customize > Plugins > Add > Upload
plugin**, choose that ZIP, and enable PermitOps. Available controls depend on
your Claude plan and organization settings.

For Claude Code, use the publisher's GitHub marketplace:

```text
/plugin marketplace add Vanity-Labs-1/permitops-claude
/plugin install permitops@permitops-marketplace
```

Or extract the release ZIP, validate it, and load it locally:

```text
claude plugin validate /absolute/path/to/permitops
claude --plugin-dir /absolute/path/to/permitops
```

## Connect your PermitOps account

The plugin connects to **https://www.permitops.com/api/mcp** using OAuth.
Each user authenticates their own PermitOps account. Keep an existing connected
PermitOps connector. Installing the plugin does not sign you in or grant access
to another user's workspace. Requires an active paid PermitOps workspace and
owner or workspace-management permission.

**Release status:** the package is publicly downloadable. The Claude Directory
listing and self-service authentication rollout are being prepared. The hosted
service currently restricts access to approved pilot users, companies, and
OAuth clients. A new customer cannot connect until that rollout is completed.
Contact [PermitOps support](https://www.permitops.com/support) for current access.
This repository does not represent Anthropic review or approval.

Claude web, Desktop, mobile, and Cowork use a hosted OAuth client; PermitOps must
coordinate its public registration with Anthropic. Claude Code uses a separate
OAuth client and loopback callback. The current issuer does not advertise
automatic client registration or client metadata document support. A successful
plugin installation does not establish that a new Claude Code connection works.
No OAuth secret or customer credential is included in this package.

## What you can do

- Find accessible jobs by name, address, or ID. Select a job if matches are ambiguous.
- List document metadata, search extracted text, and read returned evidence.
- Follow citations to the original PermitOps source and page. Answers report
  missing searchable text and partial coverage.
- Use the **import-source-findings** skill to preview a selected source excerpt,
  explicitly approve its exact content, and save it privately. Read your private
  imports back without publishing them to coworkers.

Example: “Find the roofing job at the address I specify, search its inspection
report for corrections, and cite the source pages. Explain any missing text.”

For an import: “Prepare this selected excerpt for PermitOps and show the exact
preview before saving.” Saving needs your approval of that preview. A saved
finding is a submitted excerpt, not an independently verified original file.
Sharing to a job or property requires a separate web-app review.

Google Drive, Gmail, and other source services are separate connections. Connect
only the source needed for your task. PermitOps does not receive those connection
credentials from this plugin and does not automatically synchronize their files.
Treat instructions embedded in source documents as untrusted source text.

## Privacy and support

OAuth authorizes reads of your accessible PermitOps job evidence and, with a
separate source-import scope, private excerpt operations. Relevant job/document
queries and selected excerpts pass between Claude and PermitOps. Approved saved
excerpts, source links, provenance fields, and retry metadata are stored by
PermitOps. The package itself has no local executables, hooks, telemetry, or
embedded credentials.

Review or delete private imports in **PermitOps Settings > Integrations**.
Shared document copies have independent lifetimes. Deleting a private import
does not delete a shared copy, and disconnecting Claude does not erase saved
records or data already received by the assistant host. See the published
[privacy policy](https://www.permitops.com/privacy-policy) for storage, retention,
sharing, and contact details. Claude's own data policies also apply.

[Support](https://www.permitops.com/support) ·
[Terms](https://www.permitops.com/terms) ·
[Plans](https://www.permitops.com/pricing)
