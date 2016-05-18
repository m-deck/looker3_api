Python Library for Looker 3.0 API
=================================


Setup
-----

You can install this package by cloning/downloading this directory and running:

   ```$ python setup.py install```
   
from a terminal within the directory


Getting Looker API keys
-----------------------

Within your Looker, navigate to admin, manager users, then either create a new API user or get the token and secret associated with an existing API user.


Using the Looker Python Library
-------------------------------

    from looker_client import LookerClient

    # Instantiate and Login to Looker
    
    lc = LookerClient('looker_token', 'looker_secret', 'https://avant.looker.com', limit=100, port=19999)
    
    # Get a DataFrame from a long share url
    
    url = 'long_share_url_from_explore'
    
    df = lc.get_df_from_long_share_url(url)
    
    # Get a DataFrame from a short url
    
    # NOTE: limit DOES NOT WORK FOR SHORT URLS. Set the row limit within looker before accessing the share link
    
    url = 'short_url_from_share_menu'
    
    df = lc.get_df_from_slug(short_url)
