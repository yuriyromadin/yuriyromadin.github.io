---
layout: post
title:  "Website redirects after migrating to another domain"
date:   2018-08-03 19:03:46 +0300
permalink: s3-static-website-redirect
comments: true
background: /assets/img/staticwebsitehosting-background.jpg
---
Imagine you need to migrate your old website to the new domain name.
For example, your old blog was located at blog.example.com, but now it needs to
be under your main domain name: example.com/blog

In order to save your hard earned position in search, you have to set up correct
redirects from old website to the new one:

[blog.example.com/best-recipes/](#)

becomes

[example.com/blog/best-recipes/](#)

But how would you set up this quickly and painlessly?

Obvious and correct solution would be set up those redirecrts directly on the
new web server.

But what if you don't have access to the new server configuration or don't want to fiddle with the settings on it?

You can of course, use numerous online solutions, paid or free, that offer this type of functionality, but free services can dissaper anytime and paid will just burn a hole in your pocket.

## Amazon to the rescue!

As you probably know, Amazon not only the world's largest retailer, but they also provide web services.
We can take advantage of [S3's static website functionality](https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html).

It allows you to host static website for almost for free (typically, it will cost around $1/month).

## Setup

1. Sign in to the AWS Management Console and open the [Amazon S3 console](https://console.aws.amazon.com/s3/).
2. In the list, choose the bucket that you want to use for your hosted website.
3. Choose the **Properties** tab.
4. Choose **Static website hosting**, and then choose **Use this bucket to host a website**.

![My helpful screenshot]({{ "/assets/img/staticwebsitehosting.png" | absolute_url }})

### Where the magic happens

You may notice that there's special field, called *Redirection rules* and this is what we are looking for!

The field syntax looks complex on the first glance, but is pretty trivial:

{% highlight xml %}
<RoutingRules>
  <RoutingRule>
    <Condition>
      <KeyPrefixEquals>best-recipes/</KeyPrefixEquals>
    </Condition>
    <Redirect>
      <HostName>example.com</HostName>
      <ReplaceKeyPrefixWith>blog/best-recipes/</ReplaceKeyPrefixWith>
    </Redirect>
  </RoutingRule>
</RoutingRules>
{% endhighlight %}

It's pretty basic XML syntax, and you can add as many *RoutingRule*'s as you wish:

{% highlight xml %}
<RoutingRules>

  <RoutingRule>
    <Condition>
      <KeyPrefixEquals>best-recipes/</KeyPrefixEquals>
    </Condition>
    <Redirect>
      <HostName>example.com</HostName>
      <ReplaceKeyPrefixWith>blog/best-recipes/</ReplaceKeyPrefixWith>
    </Redirect>
  </RoutingRule>

  <RoutingRule>
    <Condition>
      <KeyPrefixEquals>worst-recipes/</KeyPrefixEquals>
    </Condition>
    <Redirect>
      <HostName>example.com</HostName>
      <ReplaceKeyPrefixWith>blog/worst-recipes/</ReplaceKeyPrefixWith>
    </Redirect>
  </RoutingRule>

</RoutingRules>
{% endhighlight %}


### Finishing touches

Now, when everything is set up, last step is to point your domain to your new static website.
Easiest way is [when your bucket name is the same as your domain name.](https://docs.aws.amazon.com/AmazonS3/latest/dev/VirtualHosting.html#VirtualHostingCustomURLs)


{% highlight bash %}

blog.example.com CNAME blog.example.com.s3-website-us-east-1.amazonaws.com

{% endhighlight %}

Now when users visit old link like this: [blog.example.com/best-recipes/](http://blog.example.com/best-recipes/), they will be instantly
redirected (with the correct HTTP status code) to your new website [example.com/blog/best-recipes/](http://example.com/blog/best-recipes/)
