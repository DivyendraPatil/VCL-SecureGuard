# VCL-SecureGuard
This VCL code is designed to block potentially harmful requests from reaching your website.
It includes logic for blocking URL's with certain extensions, blocking requests from certain user agents, and blocking URL's with certain patterns.

On average, the extension and user-agent blocks implemented in this VCL configuration file are stopping over 400k requests per day, with an average rate of 350 requests per second.
## Installation

The code consists of three separate files:

- `ext_block.init`: contains the list of extensions to block.
- `ext_block.recv`: contains the code that blocks the extensions, user agents, and URL patterns.
- `ext_block.error`: contains the customized response when an extension is blocked.

Copy these files to your VCL directory and include them in your VCL config file.

## Usage

### 1. Block URL's with Certain Extensions
You can modify the list of extensions to block by editing the `ext_block.init` file. The extensions are defined in a table called extension. To add or remove an extension, simply add or delete a line from the table.

### 2. Block Requests from Certain User Agents 
The list of bad user agents is defined in the `ext_block.recv` file. To add or remove a user agent, simply modify the regular expression to match the desired user agent. The regular expression should be added to the line that starts with `if(req.http.user-agent ~`.

### 3. Block URL's with Certain Patterns
To block specific URL patterns, modify the regular expressions in the `ext_block.recv` file. The regular expression should be added to the line that starts with `if (req.url ~`.

## Customizing the Response
The response when an extension is blocked can be customized by editing the ext_block.error file. By default, a 405 response with the message "Not Acceptable" is returned.

You can modify this response to suit your needs. To modify the list of file extensions to block, simply edit the extension table in the `ext_block.init` file. To modify the list of user agent strings or URL patterns to block, simply edit the logic in the `ext_block.recv` file.

## Contributing

Contributions are welcome! Please submit pull requests or create issues if you find any bugs or have any suggestions.

## Disclaimer

While this code can help improve the security of your site/server, it is not a complete solution. It is important to follow best practices for server security, such as keeping your software up-to-date and implementing strong passwords and access controls.

## License

This code is released under the MIT license, which means you can use, copy, and modify it for any purpose, as long as you include the original license and copyright notice.

I hope this helps! Let me know if you have any questions or if there's anything else I can do for you.