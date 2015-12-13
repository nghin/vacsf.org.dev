The best way to deploy Jekyll powered website on github.
1. Create a development repository with the following config files:
   _config.yml:          url:    'http://nghin.github.io/vacsf.org.dev'
                         urlimg: 'http://nghin.github.io/vacsf.org.dev/images/'
   _config_site.yml:     url:    'http://vacsf.org'
                         urlimg: 'http://vacsf.org/images/'
   _config_nitrous.yml:  url:    'http://jekyll-142416.nitrousapp.com:4000'
                         urlimg: 'http://0.0.0.0:4000/images/'
2. Development build:
   just build: jekyll --config _config.yml,_config_dev.yml &
   build and serve: jekyll serve --host 127.0.0.1 --incremental --config _config.yml,_config_dev.yml &
   or build on nitrous.io: jekyll serve --host 0.0.0.0 --incremental --config _config.yml,_config_nitrous.yml &
3. Deployment build:
   jekyll build --config _config.yml,_config_site.yml &
4. Copy compiled files:
   rsync -avzh --delete  /home/nghi/Documents/Jekyll/vacsf.org.dev/_site/* /home/nghi/Documents/Jekyll/vacsf.org/
5. Push vacsf.org to github with .nojekyll

Great resource for getting unicode index of special Vietnamese characters
http://www.fileformat.info/info/unicode/char/search.htm?q=%E1%BA%A3&preview=entity

Required for jekyll 3.0
sudo gem install jekyll-paginate
gem install jekyll-gist
