# map_api_schemas

My personal notes on a presentation at RubyConf 2014, "Rapidly Mapping JSON/XML API Schemas In Ruby"
by Adam Cuppy (@acuppy)

- Speaker Deck: [https://speakerdeck.com/acuppy/xml-apis-in-ruby](https://speakerdeck.com/acuppy/xml-apis-in-ruby)
- YouTube: [https://youtu.be/1K0Pt0o9F7w](https://youtu.be/1K0Pt0o9F7w)

## What I want to do
I want to get data from API end point and convert that data so that my application can understand.

### Consume
Clear separation between Connection and Client

```
App <====> Client <====> Connection        <====> Resource
           - rounting    - Relationship manager
           - collection  - HTTP GET/POST
```

### Coerce
- Representation: entity mapping
- Use "instance-oriented" architecture, rather than monkey-patch hash.

```
 class-instance          hash-instance
App <====> Representation   <====> Client
           - App can understand    - HTTParty or Faraday
           - Subclass OpenStruct
```

---

## Resources

API

- [Google Civic API](https://developers.google.com/civic-information/docs/using_api)

Architecture

- [Representable Gem](https://github.com/apotonick/representable)
- [DeepStruct patterns](http://andreapavoni.com/blog/2013/4/create-recursive-openstruct-from-a-ruby-hash/#.VGkqY5PF8Wk)
- [Decorator Pattern in Ruby](http://nithinbekal.com/posts/ruby-decorators/)

HTTP client:

- [jnunemaker/httparty](https://github.com/jnunemaker/httparty)
- [lostisland/faraday](https://github.com/lostisland/faraday)
