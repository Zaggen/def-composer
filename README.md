# def-composer
Module for creating and extending classes/objects from other objects/classes

This will be an alternate syntax to the one used in the bakeIn repo, but it will have the same functionality, or at least that is the plan.

```coffeescript
def('BaseClass').compose(
  attr1: true
  attr2: false
  constructor: ->
    # do something
)

def('someObject').compose(
  public: true
  publich2: ->
)


def('User').compose(
  BaseClass, ['attr1', 'attr2'],
  OtherClass, ['public', 'publich2'],
  constructor: ->
  fn: (x)->
    x * 2
)

zaggen = new User()
```

Or maybe an even cleaner syntax, like this 

```coffeescript
def('User')(
  # Inherit(Classes)
  BaseClass, ['attr1', 'attr2'],
  OtherClass, ['public', 'publich2'],
  # Inherit(Traits)
  movable, ['*']
  # Properties
  constructor: ->
  fn: (x)->
    x * 2
)
zaggen = new User()
```
Or if you don't need to specify what you inherit, you can use like this
```coffeescript
def('User')( BaseClass, OtherClass,{
  constructor: ->
  fn: (x)->
    x * 2
});

zaggen = new User()
```

I'll be working on this, soon... maybe?
