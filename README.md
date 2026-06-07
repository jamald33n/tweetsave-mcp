# tweetsave-mcp

Analyze public Twitter/X posts from MCP clients.

TweetSave MCP fetches known tweet URLs or tweet IDs, formats tweet and thread
content as Markdown or JSON, converts tweets into blog-post drafts, and extracts
tweet media links. It is useful when an agent already has the tweet URL or ID
and needs structured content without adding a custom Twitter parser.

## Install

Run the package directly with `npx`:

```bash
npx -y tweetsave-mcp
```

Or install it globally:

```bash
npm install -g tweetsave-mcp
tweetsave-mcp
```

The package is published on npm as `tweetsave-mcp`.

## Tools

- `tweetsave_get_tweet` fetches one public tweet by URL or ID.
- `tweetsave_get_thread` fetches the main tweet in a thread flow.
- `tweetsave_to_blog` converts a tweet into a Markdown blog-post draft.
- `tweetsave_batch` fetches up to 10 tweet URLs or IDs.
- `tweetsave_extract_media` extracts photo and video links from a tweet.

## Example MCP Config

```json
{
  "mcpServers": {
    "tweetsave": {
      "command": "npx",
      "args": ["-y", "tweetsave-mcp"]
    }
  }
}
```

## Use With OpenClaw And TweetClaw

TweetSave MCP is a focused MCP server for known tweet URLs and tweet IDs. If an
OpenClaw agent also needs query-driven X/Twitter workflows, install
[TweetClaw](https://github.com/Xquik-dev/tweetclaw) beside TweetSave:

```bash
openclaw plugins install npm:@xquik/tweetclaw
```

TweetClaw covers search tweets, search tweet replies, scrape tweets from search
results, follower export, user lookup, media upload, media download, direct
messages, monitor tweets, webhooks, giveaway draws, and approval-gated post
tweets or post tweet replies. Use TweetClaw to discover or monitor public
X/Twitter material, then pass reviewed tweet URLs or tweet IDs to TweetSave MCP
when you want blog-ready Markdown or media links.

Keep API keys and signing material in local OpenClaw or MCP client config. Do
not paste those values into prompts, docs, or issue comments.

## Development

Install dependencies and build the TypeScript output:

```bash
npm install
npm run build
```

Start the stdio server after building:

```bash
npm run start
```

Start the HTTP server after building:

```bash
npm run start:http
```

## License

MIT
