# Lua modules

Some my modules for Lua which I wanted to share with everyone else.

# Class

Best module, IMHO. Implements nice-styled classes.

Idea was taken from Rosetta Code and when I don't saw any workable implementations of this.

Example:

```lua
require 'class'

class 'MyClass' {
	function(this)
		print(this)
	end,

	method = function(this, ...)
		this:other()
	end,
}

class 'Parent' : inherits 'MyClass' {
	-- default constructor automatically does this:super()
	--function(this)
	--  this:super()
	--end,

	other = function(this)
		print 'yee'
	end,
}

local parent = new 'Parent' ()
parent:method()
```

# Dump

Simple module, just dumps strings and tables.
Just try `print(dump(somewhatLongAndUsefulTable))`.

# Events

Events handler based on my class library.
Have 2 classes: `Events` and `EventsThis`.
You can read more about them directly in code or in automatically
generated documentation with LDoc.

# Multipart

Useful utility to send multipart (form-data) things over HTTP/HTTPS.
Just use
```lua
mp.encode {
	key = 'value',
	-- etc...
	file = {
		filename = 'file.json',
		-- contentType = 'application/json',
		data = '<your file contents>'
	},
}
```
