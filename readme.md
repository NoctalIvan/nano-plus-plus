NANO++ - Simplest Template Engine, now with array template!
=============================

***Basic Usage***

Assuming you have following JSON response:

<pre>
data = {
  user: {
    login: "tomek",
    first_name: "Thomas",
    last_name: "Mazur",
    account: {
      status: "active",
      expires_at: "2009-12-31"
    }
  }
}
</pre>

you can make:

<code>
  nano("&lt;p&gt;Hello {user.first_name} {user.last_name}! Your account is &lt;strong&gt;{user.account.status}&lt;/strong&gt;&lt;/p&gt;", data)
</code>

and you get ready string:

<code>
  &lt;p&gt;Hello Thomas Mazur! Your account is &lt;strong&gt;active&lt;/strong&gt;&lt;/p&gt;
</code>

Simple huh?

***Array matching***

And now with NANO++, you can also match arrays!

The syntax is simple, match the following data :

<code>
data = {
  users: [
  	{
  		first_name: "Thomas",
  		last_name: "Mazur"
  	},
  	{
  		first_name: "Ivan",
  		last_name: "Sedletzki"
  	}
  ]
}
</code>

... with the following template :

```html
	
<ul>
	[{users}
		<li>Hello {first_name} {last_name}</li>
	]
</ul>
	
```

... to get 

<code>

	- Hello Thomas Mazur
	- Hello Ivan Sedletzki

</code>

See the test page: <a href="testPage.html">testPage.html</a> for a complete exemple.

Endless thanks to Trix (https://github.com/trix) for the original NANO template engine
