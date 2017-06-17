ArriveLah
===

Fast simple API for bus arrival times in Singapore.

This is like a proxy to [LTA's DataMall Bus Arrival API](http://www.mytransport.sg/content/mytransport/home/dataMall.html).

API
---

### Request

<https://arrivelah.herokuapp.com/?id=83139>

- `id` - (required) Bus stop ID/code

### Response

```json
{
  "services": [
    {
      "no": "15",
      "next": {
        "time": "2015-04-30T11:05:10+00:00",
        "duration_ms": 796176
      },
      "subsequent": {
        "time": "2015-04-30T11:05:38+00:00",
        "duration_ms": 824176
      }
    },
    {
      "no": "155",
      "next": {
        "time": "2015-04-30T10:51:32+00:00",
        "duration_ms": -21825
      },
      "subsequent": {
        "time": "2015-04-30T11:00:34+00:00",
        "duration_ms": 520175
      }
    }
  ]
}
```

The responses are cached for **15 seconds**.

Development
---

1. Add configuration. Follow documentation from [mytransport.sg DataMall](http://www.mytransport.sg/content/mytransport/home/dataMall.html). Two options (choose one):
  1. Copy and rename `.env.example` to `.env`. Edit the file.
  2. Add environment variables.
2. `npm install`
3. `npm start`
4. Load `locahost:8081`. Change `PORT` in configuration if it doesn't work.

License
---

[MIT](http://cheeaun.mit-license.org/). Data is copyrighted by [LTA](http://www.mytransport.sg/).
