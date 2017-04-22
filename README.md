# PiNet documentation website
The PiNet documentation website is built using Jekyll. If you would like to contribute to the documentation, please check [here](http://pinet.org.uk/articles/CONTRIBUTING.html).
    
The main site can be found at [http://PiNet.org.uk](http://PiNet.org.uk).

## Found a mistake or want to contribute to the documentation?
Check out the [PiNet documentation contribution page](http://pinet.org.uk/articles/CONTRIBUTING.html) for details on how to get involved!

# Running site locally

## Installing Jekyll and dependancies.
To run the site locally, 
- First [install Ruby](https://www.ruby-lang.org/en/documentation/installation/).   
- Then install bundler ```gem install bundler```.   
- Finally install Jekyll ```gem install jekyll```.   
- Grab the documentation site ```git clone https://github.com/PiNet/PiNet.github.io.git```
- Use bundler to make sure you have all the required gems ```bundle install --binstubs```

## Running development server
To run the development server - ```./bin/jekyll serve watch```   
Then navigate to ```http://localhost:4000/``` in a web browser.


# License
The PiNet documentation is released under the MIT License. Check the [LICENSE](LICENSE) file for more information.
