# PDFLean MCP Server

[![TensorBlock MCP Index](https://mcp-index.tensorblock.co/v1/servers/github-epengwang-pdflean-mcp-c12575cb/badge.svg)](https://tensorblock.co/mcp/servers/github-epengwang-pdflean-mcp-c12575cb)

Hosted remote MCP server that gives AI agents 17 PDF tools: validate, extract, merge, split, compress, OCR, sign and redact.

- **Endpoint:** `https://mcp.pdflean.com/mcp` (Streamable HTTP, stateless)
- **Authentication:** OAuth 2.1 (dynamic client registration + PKCE), scopes `pdflean:read` / `pdflean:write`
- **Official MCP Registry:** `com.pdflean/mcp`
- **Website:** https://pdflean.com

## Connect

Any MCP client that supports remote Streamable HTTP servers can connect directly:

```json
{
  "mcpServers": {
    "pdflean": {
      "url": "https://mcp.pdflean.com/mcp"
    }
  }
}
```

On first use the client opens the PDFLean OAuth consent page; sign in with a PDFLean account and approve access. Tool usage is metered in PDFLean API credits; status and usage tools are free.

## Tools

Read-only:

| Tool | Purpose |
| --- | --- |
| `pdf_validate_pdfa` | Validate a PDF against PDF/A |
| `pdf_check_accessibility` | Check PDF/UA accessibility |
| `pdf_verify_signature` | Verify digital signatures |
| `pdf_extract_text` | Extract text and structured form/invoice fields |
| `pdf_scan_pii` | Scan a document for personal data |
| `ai_summarize` | Summarize a document |
| `ai_translate` | Translate a document |
| `job_status` | Check an async job (free) |
| `credits_usage` | Check credit usage (free) |

Write:

| Tool | Purpose |
| --- | --- |
| `pdf_merge` | Merge multiple PDFs |
| `pdf_split` | Split a PDF |
| `pdf_compress` | Compress a PDF |
| `pdf_convert_document` | Convert Office documents to/from PDF |
| `pdf_ocr` | OCR scanned documents |
| `pdf_sign` | Digitally sign a PDF |
| `pdf_redact` | Redact sensitive content |
| `workflow_run` | Run a saved PDFLean workflow |

## Notes

This repository is the public listing for the hosted service: it contains the registry manifest (`server.json`) and client configuration examples. The server itself runs at the endpoint above; there is nothing to install or self-host.
