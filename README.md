# nostr-n8n

Nostr is a new protocol for adding a social layer to the Internet. n8n is a workflow automation tool. This repository contains workflows which use n8n with Nostr to augment a Nostr user's experience on the network.

My intent it to publish a variety of useful workflows.

At this time there is one workflow which allows you to create your own Nostr AI Assistant.

## Prerequisites

- **n8n**: Install a self-hosted n8n on your system. You can follow the instructions from the [n8n website](https://docs.n8n.io/hosting/),
- **Nostrobots**: Install [Nostrobots Community Nodes](https://github.com/ocknamo/n8n-nodes-nostrobots/tree/main) by [Ocknamo](https://njump.me/npub1y6aja0kkc4fdvuxgqjcdv4fx0v7xv2epuqnddey2eyaxquznp9vq0tp75l) with instructions from the [n8n website](https://docs.n8n.io/integrations/community-nodes/installation/),
- **Add workflow from Github to n8n**: For the workflow of your choice 1. In Github copy the URL for the Raw .json, 2. In n8n create a new workflow, then click "..." and "Import from URL",
- **Credentials**: Add whatever credentials are required by the Nodes,
- **Setting**: Specify whatever settings are required by the workflow. Typically all required settings are placed in a "Set" Node at the start of the workflow following the Trigger Node.

## n8n Workflows

### Nostr AI Assistant
The Nostr AI Assistant workflow powers a Npub of your choosing to become your Assistant, and respond to your Notes when Mentioned. 

You can use this to get all the functionality of a "chat-gpt-like" LLM AI assistant interface, without having to leave your Nostr client.

Assistant can read and summarise long threads and articles, query the internet and provide links, perform calculations, help you understand notes, translate foreign languages, etc – In general, it allows you to use your Nostr client as a Web UI for an LLM and bring that LLM into conversation into a context with your friends and followers on Nostr.

This workflow triggers your AI Assistant to respond to Notes on Nostr, if–

- Assistant Npub is Mentioned in a Note (the user shows intent),
- User is the Owner of Assistant (the user is authorised),
- Tagged Note is not the child of another tagged Note (if Note is threaded, reply to end of thread),
- Tagged Note has not yet been replied to by assistant (for deduplication),
- We run this workflow periodically or if triggered.

#### Set up

- **Prerequisites**: Complete the prerequisites as above to have a working n8n instance with Nostrobots Community Nodes installed,
- **Create Assistant Nostr Profile**: Create a new Nostr profile to be the Assistant, backup the npub and nsec keys,
- **Add cedentials for n8n**: Add credentials to n8n for Nostr, Anthropic, SerpAPI. Nostrobots accepts the Nostr profile Nsec as its credentials,
- **Set workflow variables in the Set Variables Node**: Add Owner Npub, Assistant Npub, Assistant Name, Relays,
- **Test Workflow**: 1. Create a Note on Nostr that Mentions the Npub of Assistant. 2. Click "Test Workflow" in n8n,
- **Go Live**: Turn workflow to Active.

## To Do

- Further enhancements to Nostr AI Assistant workflow,
- Further Nostr n8n workflows.

## Nostr profiles

- Contact me [npub1r0d8u8mnj6769500nypnm28a9hpk9qg8jr0ehe30tygr3wuhcnvs4rfsft](http://njump.me/npub1r0d8u8mnj6769500nypnm28a9hpk9qg8jr0ehe30tygr3wuhcnvs4rfsft),
- See an example "Jonny (AI Assistant)" live [npub1ahjpx53ewavp23g5zj9jgyfrpr8djmgjzg5mpe4xd0z69dqvq0kq2lf353](http://njump.me/npub1ahjpx53ewavp23g5zj9jgyfrpr8djmgjzg5mpe4xd0z69dqvq0kq2lf353).

## License

- This project is licensed under the MIT License.