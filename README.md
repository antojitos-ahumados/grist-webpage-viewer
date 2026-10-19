# Web page viewer

A custom widget for [Grist](https://www.getgrist.com/) that shows the web page whose URL is stored in the selected record. It sits beside the table so you can read linked pages without leaving the document.

The published widget is:

https://antojitos-ahumados.github.io/grist-webpage-viewer/index.html

Source: https://github.com/antojitos-ahumados/grist-webpage-viewer

## Add it in Grist

1. Choose **Add widget**.
2. Choose **Custom**.
3. Enter `https://antojitos-ahumados.github.io/grist-webpage-viewer/index.html`.
4. Set the access level to **Read selected table**.
5. Map the **URL** column to the column that holds web addresses.

Link the widget to the table with **Select by**, or place it on the same table, so the selected record chooses the page.

## Supported URL formats

The mapped column may contain:

- A full `http` or `https` address, such as `https://www.getgrist.com/`.
- A bare domain and optional path with no scheme, such as `www.getgrist.com/`. It is loaded with `https`.
- A Hyperlink value written as a label followed by a URL, such as `Docs https://www.getgrist.com/`. The trailing URL is used.

Only `http` and `https` addresses are loaded. Other schemes, including `javascript:` and `data:`, are refused. An empty cell, or a value that is not a web address, shows a short message instead of a page.

A bar above the page shows the current address and an **Open in new tab** link. Changing other cells in the same record does not reload the page. The page loads in a sandboxed iframe that cannot navigate the Grist page, and the request is sent with no referrer.

## Limitation

Sites that forbid iframe embedding, through `X-Frame-Options` or a Content-Security-Policy `frame-ancestors` directive, will not display. The frame stays blank; use **Open in new tab**.

## License

Apache License, Version 2.0. See [LICENSE](LICENSE).
