# Wii U Root Store

This is a repo of certificates to keep the Wii U Internet Browser alive

Plugin (Aroma Environment): coming soon<sup>tm</sup> (legit)

## Requirements (for more information on reasons why things are as is, look at notices below)
1. Certificates must be in the .der format
  - While there is a PEM function it doesn't seem to work (as least for me)
2. Certificate has Encryption RSA and not ECDSA
  - OpenSSL Version is too old to support

## Adding Certs
- I guess try to think about if it should be in the repository or if it should get it from a url (that shouldn't change to not break updates)
1. Add the cert file to the certs folder and make a pr
2. Add a item to the certs.json file and submit a pr

## TODO
- Make GitHub Action so it will compile to pages
- Make Versioning System
  - Can add notifications for when theres a new update to the root store
- 1st Version will download a whole zip and unzip it for new updates but should try to make it so it doesn't download the whole thing each time when i have time for that (<-- would be better for users with metered internet)
- Planning to make two systems for certs
  - One will be just adding ders to the repository in the certs folder
  - The other one a json list to get it from the source (for example GTS Certs and getting them from pki.goog) 
    - Not doing this currently as i am too lazy atm: Also would need to cache them as well so we (look down at these reasons). BUT! We also need to make it so the cache dies maybe after a few months or if its expiration date (on a certificate) is near don't cache on that 
      1. Don't get ratelimted for some reason by services
      2. moar fast gh actions and faster updates
- Make like an indexer where people can submit links and direct files via github issues or something
