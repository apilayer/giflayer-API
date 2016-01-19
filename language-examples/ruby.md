# Language Examples

## Ruby

### Capture GIF via Ruby:

Find below a Ruby function that lets you capture a GIF and define all required and optional parameters:

```php
require 'cgi' unless defined?(CGI)
 
def giflayer(url, options={})
    
  # set access key
  access_key = 'YOUR_ACCESS_KEY'
  
  # define parameters
  parameters = {
    :url       => url,
    :start  => options[:start],
    :end  => options[:end],
    :duration  => options[:duration],
    :size  => options[:size],
    :crop  => options[:crop],
    :fps  => options[:fps],
    :trailer  => options[:trailer],
    :export  => options[:export],
  }
   
  query = parameters.
    sort_by {|s| s[0].to_s }. 
    select {|s| s[1] }.       
    map {|s| s.map {|v| CGI::escape(v.to_s) }.join('=') }.
    join('&')
  
  "http://apilayer.net/api/capture?access_key=#{access_key}&#{query}"
end
 
# set url (required), optional parameters (leave blank if unused) & call function
puts giflayer("https://www.youtube.com/watch?v=3W6hZR29l5o",{ 
    start: "", 
    end: "", 
    duration: "", 
    size: "", 
    crop: "", 
    fps: "", 
    trailer: "", 
    export: "" })     
```
