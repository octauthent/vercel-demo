# Vercel ✕ Octauthent Demo

Hi there 👋

Welcome the Vercel ✕ Octauthent demo!

You can access everything, except URLs starting with `/private`, such as [this post](https://vercel.octauthent.com/private/2021/07/20/private-post.html).

## Credentials

If you want to access the [private post](https://vercel.octauthent.com/private/2021/07/20/private-post.html), you'll need the following credentials:

**username**: `demo`

**password**: `octauthent`

## How it works

This website is nothing more than the [sample Jekyll blog](https://github.com/vercel/vercel/tree/main/examples/jekyll) provided by Vercel.

There is absolutely no code related to authentication, so everybody could (normally) access the private post.

However, thanks to [Octauthent](https://octauthent.com), here is what happens when you access `vercel.octauthent.com/private/*` from your browser:

1.  A DNS server recognizes the domain and responds with **a Cloudflare IP**
2.  Your browser **asks for the page** to the Cloudflare IP it received
3.  Cloudflare **runs the Octauthent code** to know what to do
4.  If Octauthent decides that **you are not allowed**, Cloudflare **responds with a customized login form**
5.  If Octauthent decides that **the page can be seen**:
    1.  Cloudflare **asks to Vercel** the content of the page
    2.  Vercel recognizes the address and **responds with the page content**
    3.  Cloudflare **sends the response** back to your browser
