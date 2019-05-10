# The `_data/places` folder

This folder contains information about each [place](https://schema.org/Place) your Web site knows about. You can teach your Web site about new places by adding files in this folder with the place's details. Then, you can reference the place by `name` in other parts of your Web site, such as the `location` of [events](../../_events/).

A place file is a [Jekyll data file](https://jekyllrb.com/docs/datafiles/) that describes a place, such as a venue where an event is held. For example, the following content creates [a place called "My Bar"](my-bar.yaml) with an address, homepage link, logo image, and associated Facebook page:

```yaml
name: My Bar
type: BarOrPub
address:
    streetAddress: 123 Main Street
    addressLocality: Pleasantville
    addressRegion: NY
    postalCode: 12345
    addressCountry: United States
url: https://myvenue.com/
logo: https://myvenue.com/venue-logo.jpg
sameAs:
    - https://www.facebook.com/MyVenue
```

The fields of a place are the same as the [Schema.org `Place` object](https://schema.org/Place).

Now you can use this place's `name` (i.e., `My Bar`) as the value for a `location` of an event:

```yaml
---
startDate: 2019-05-09 16:00:00 -0400
endDate: 2019-05-09 17:00:00 -0400
location: My Bar
---

My example event at My Bar.
```
