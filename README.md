# elixirPhoenixService
A Elixir/Phoenix service that retrieves and stores data about elected officials and elections throughout the United States

```ruby
base_uri 'http://openstates.org/api/v1'
API_KEY = {apikey: '70bac8cac7134681a9513271c2450733'}
FIELDS = "first_name,middle_name,last_name,photo_url,leg_id,url,offices"

def initialize(state)
end

def self.all_legs(state)
  self.get('/legislators', {query: {state: state, fields: FIELDS}.merge(API_KEY)})
end

def self.by_geo(lat, long)
  location = {query: {lat: lat, long: long, fields: FIELDS}.merge(API_KEY)}
  self.get('/legislators/geo', location)
end
```
