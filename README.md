JsMockito
---------

  http://github.com/chrisleishman/jsmockito/tree/master


JsMockito is a JavaScript stub/mock framework inspired by Mockito. 
To quote the mockito website:

  "Mockito is a mocking framework that tastes really good.  It
   lets you write beautiful tests with a clean & simple API.
   Mockito doesn't give you a hangover because the tests are
   very readable and they produce clean verification errors."

JsMockito aims to try and reproduce the clean & simple API, with
a JavaScript twist.  And why not add some variation to your
drinking habits?


What do you serve it with?
--------------------------

JsMockito must be served with JsHamcrest.  No only do they go well
together, it's essential to avoid a very nasty hangover.  Get
JsHamcrest from here:

  http://github.com/danielfm/jshamcrest/


How to drink it?
----------------

To use JsMockito with a JavaScript unit test framework, follow the
usual installation/configuration instructions for the framework
and plug JsMockito into it.  If you're integrating with Screw.Unit
(and why wouldn't you?) then more detailed instructions are below.

Once installed, you can verify with interactions:

    var mockedObject = mock(Array);
     
    // -- start code under test --
    mockedObject.push("one");
    // -- end code under test --
     
    verify(mockedObject).push("one");


Or you can stub method calls:

    var mockObject = mock(MyClass);
     
    when(mockObject).get(1).thenReturn("hello world");
     
    // -- start code under test --
    alert(mockedObject.getGreeting("initial"));
     
    // the following alerts 'true' as get(99) was not stubbed
    alert(typeof (mockedObject.get(99)) === 'undefined');
    // -- end code under test --


For a JavaScript twist, you can also mock functions:

    mockFunc = mockFunction();
    when(mockFunc).call(this, anything()).then(function(arg) {
      return "foo " + arg;
    });
     
    // -- start code under test --
    mockFunc("bar");
    // -- end code under test --
     
    verify(mockFunc).call(this, anything());
 

For more examples and documentation, look in the doc directory.


Who is your bartender?
----------------------

This variation is served to you by Chris Leishman and friends.  Also a big
thumbs up and thanks to the mockito guys for the inspiration!

Also thanks to the JsHamcrest authors, who made this easy.