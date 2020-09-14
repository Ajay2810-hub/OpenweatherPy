OpenweatherPy
=============

.. image:: https://img.shields.io/pypi/v/openweatherpy.svg?style=flat-square
    :target: https://pypi.org/project/openweatherpy
    :alt: Latest PyPI version

.. image:: https://pepy.tech/badge/openweatherpy
    :target: https://pepy.tech/project/openweatherpy
    :alt: Downloads

.. image:: https://pepy.tech/badge/openweatherpy/month
    :target: https://pepy.tech/project/openweatherpy/month
    :alt: Downloads

.. image:: https://pepy.tech/badge/openweatherpy/week
    :target: https://pepy.tech/project/openweatherpy/week
    :alt: Downloads

.. image:: https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square
    :target: https://opensource.org/licenses/MIT
    :alt: MIT License

.. image:: https://img.shields.io/pypi/pyversions/openweatherpy.svg?style=flat-square
    :target: https://pypi.org/project/openweatherpy
    :alt: Supported Python versions

.. contents:: **Table of Contents**
    :backlinks: none

About
-----

This project retrieves the weather data from openweathermap.org in JSON
format. It also provides data in different languages and in different
units like Fahrenheit, Celsius and Kelvin.

Requirements
------------

Ensure that you have an openweathermap.org Api key. If not, then `click
here <https://openweathermap.org/api>`__ to generate one.

::

     python>=3.0

Installation
------------

.. code-block:: python

     pip install openweatherpy

Dependencies
------------

::

     requests

Usage
-----

.. code-block:: python

     from OpenweatherPy import Weather
     weather = WeatherPy('API_KEY')

**Get report of a city or a country**

.. code-block:: python

     city = weather.query(city='City Name') #Get weather report of a city

     country = weather.query(country='Country Code') #Get weather report of a country

     location = weather.query(city='City Name', country='Country Code') #City and Country keywords and can be used at a same time

**Get weather and it's description**

.. code-block:: python

     mumbai = weather.query(city='mumbai')

     mumbai.weather
     mumbai.description

Output:

::

     Clouds
     broken clouds

**Get temperature, pressure, humidity, max temperature, min temperature**

.. code-block:: python

     mumbai.temperature
     mumbai.pressure
     mumbai.humidity
     mumbai.temp_max
     mumbai.temp_min

Output:

::

     289.57
     1018.0
     72.0
     290.37
     288.71

**Get co-ordinates**

.. code-block:: python

     mumbai.co_ordinates

Output:

::

     {'lon': 72.85, 'lat': 19.01}

**Get cloudiness, sunrise time, sunset time and timezone**

.. code-block:: python

     mumbai.clouds
     mumbai.sunrise
     mumbai.sunset
     mumbai.timezone

Output:

::

     {'all': 75}
     1599872150
     1599916449
     19800

**Note**: The sunrise, sunset and timezone are as per UTC time.

**Get wind details**

.. code-block:: python

     mumbai.wind

Output:

::

     {'speed': 4.1, 'deg': 150, 'gust': 9.3}

**Get city Id**

.. code-block:: python

     mumbai.id

Output:

::

     1275339

**Get weather report of location by Id**

.. code-block:: python

     manhattan = weather.getbyid(5125771) 

**Get weather report of a location by geographical co-ordinates i.e latitude and longitude**

.. code-block:: python

     delhi = weather.coords(lat=28.67, lon=77.22) 

**Get weather report in different language**

The default language is english (en).

.. code-block:: python

     weather = WeatherPy('API_KEY', lang='hi') 

**Get weather report in different unit**

The default unit is Kelvin and optional are celsius and fahrenheit.

.. code-block:: python

     weather = WeatherPy('API_KEY', unit='Fahrenheit', lang='hi') 

**Get all language codes**

.. code-block::python

    weather.languages() 

Output:

::

    {
       'af': 'Afrikaans',
       'al': 'Albanian',
       'ar': 'Arabic',
       'az': 'Azerbaijani',
       'bg': 'Bulgarian',
       'ca': 'Catalan',
       'cz': 'Czech',
       'da': 'Danish',
       'de': 'German',
       'el': 'Greek',
       'en': 'English',
       'eu': 'Basque',
       'fa': 'Persian(Farsi)',
       'fi': 'Finnish',
       'fr': 'French',
       'gl': 'Galician',
       'he': 'Hebrew',
       'hi': 'Hindi',
       'hr': 'Croatian',
       'hu': 'Hungarian',
       'id': 'Indonesian',
       'it': 'Italian',
       'ja': 'Japanese',
       'kr': 'Korean',
       'la': 'Latvian',
       'lt': 'Lithuanian',
       'mk': 'Macedonian',
       'no': 'Norwegian',
       'nl': 'Dutch',
       'pl': 'Polish',
       'pt': 'Portuguese',
       'pt_br': 'Português Brasil',
       'ro': 'Romanian',
       'ru': 'Russian',
       'sv, se': 'Swedish',
       'sl': 'Slovenian',
       'sp, es': 'Spanish',
       'sr': 'Serbian',
       'th': 'Thai',
       'tr': 'Turkish',
       'ua, uk': 'Ukranian',
       'vi': 'Vietnamese',
       'zu': 'Zulu',
    }

License
-------

``openweatherpy`` is distributed under the terms of
`MIT License <https://choosealicense.com/licenses/mit>`_



