# autotrader-scraper

I needed to create a dataset to train a CNN, so I scraped autotrader.nl for car images that are properly classified.

## Installation

```
git clone git@git.looklive.org:research/autotrader-scraper.git
cd autotrader-scraper
pip install -r requirements.pip
```

## Usage

Just run:
```
./scrape.py
```

It will create an 'images' directory that contains images per make/model, like this:
```
images
├── audi-a4
│   └── audi-a4-stationwagen-benzine-zwart--98191425-Medium.jpg
├── bmw-3-serie
│   ├── bmw-3-serie-cabriolet-benzine-zwart--88075161-Medium.jpg
│   └── bmw-3-serie-stationwagen-benzine-zwart--97409188-Medium.jpg
├── bmw-5-serie
│   ├── bmw-5-serie-sedan-benzine-zwart--100091661-Medium.jpg
│   └── bmw-5-serie-stationwagen-diesel-grijs--99117880-Medium.jpg
├── citroen-c1
│   ├── citroen-c1-hatchback-benzine-blauw--97106341-Medium.jpg
│   └── citroen-c1-hatchback-benzine-grijs--99443890-Medium.jpg
├── ford-ka
│   └── ford-ka-hatchback-benzine-blauw--82061771-Medium.jpg
...
```

Downloading of images is threaded, in order to speed up the process. You can control the start/end page by passing parameters to overview_page(), like so:
```
# will scrape from page 1 to page 6000 (that's a lot of cars!)
overview_page(start=1, end=6000)
```
