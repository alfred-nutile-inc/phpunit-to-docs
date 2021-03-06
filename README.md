# PHPUnit to Docs

Quick way to turn PHPunit API tests into docs

For example


~~~
/**
 * @api
 * @test
 * @parametor:foo:string:this is a foo resource
 **
 public post_on_some_route()
 {
    $payload = [
        'foo' => 'bar',
        'baz' => 2
    ];
    
    
    $this->call('POST', '/api/v1/foo', $payload);
    
    //Do some real tests assertions here
 }
~~~

The **convetions** @api tells the documentation tool to convert this method to Markdown as well as $payload
shows a good example of the payload.

The name of the test becomes the Title on the API doc so we would end up with this markdown.

And call out Paremeter in the URL like `foo` in this case the user can know it is a string.

So `@parametor:foo:string:this is a foo resource` is really `@parametor:example in uri:type:description`

** **Example Output** **

## Post on Some Route

### Method Post 

### URI '/api/v1/foo'

### Parameters

#### foo as string

### Payload

~~~
    $payload = [
        'foo' => 'bar',
        'baz' => 2
    ];
~~~

** **End Example Output** **

Also included will be Jquery / Ajax to allow the user to use the API in the documentation page by adding @demo to the 
annotations.





