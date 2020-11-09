### GFS Redmine Administration Log

\|*. Date \|*. Who \|\_. What \|\
\| 2020/03/02 \| Linhai \| Reporter Role，allow "Edit own issues" \|\
\| 2020/03/05 \| Linhai \| Disable "Use current date as start date for
new issues"\|\
\| 2020/03/05 \| Linhai \| 24 to 48 of "Maximum number of months
displayed on the gantt chart"\|\
\| 2020/03/09 \| Linhai \| update
/redmine/redmine-4.1.0/config/configuration.yml

    <code class="yaml">
    production:
      email_delivery:
        delivery_method: :smtp
        smtp_settings:
          enable_starttls_auto: true
          address: "smtp.office365.com"
          port: 587
          domain: "outlook.com"
          authentication: :login
          user_name: "gfscold_redmine@outlook.com"
          password: "Redmine87654321"
    </code>

\
\|\
\| 2020/03/23 \| Linhai \| Add a GFS logo banner to home page

    <code class="yaml">
    /redmine/app/views/layouts/base.html.erb
    </code>

\
\|\
\| 2020/04/10 \| Linhai \| Add custom field "Client" \|\
\| 2020/04/17 \| Linhai \| install plugin
[Additionals](https://www.redmine.org/plugins/additionals)

    $ cd $REDMINE_ROOT
    $ git clone -b v2-stable git://github.com/alphanodes/additionals.git plugins/additionals
    $ bundle install --without development test
    $ bundle exec rake redmine:plugins:migrate RAILS_ENV=production

\
\|\
\| 2020/04/23 \| Linhai \| install plugin "redmine\_privacy\_terms"

    cd $REDMINE_ROOT
    git clone git://github.com/alphanodes/redmine_privacy_terms.git plugins/redmine_privacy_terms
    git clone git://github.com/alphanodes/additionals.git plugins/additionals
    bundle install --without development test
    bundle exec rake redmine:plugins:migrate RAILS_ENV=production

\
\|\
\| 2020/04/24 \| Linhai \| Enable SCM git

    <code class="yaml">
    /redmine/config/configuration.yml
    scm_git_command: /usr/local/git/bin/git
    </code>

\
\|\
\| 2020/04/26 \| Linhai \| Run webserver with puma instead of webrick

    /redmine/Gemfile add line
    gem 'puma', '~> 3.7'

    bundle install

    /etc/init.d/start-redmine.sh
    bundle exec rails server -p 3080 puma -e production &

\
\|\
\| 2020/05/09 \| Linhai \| install plugins
"redhopper","Scrum2B","custom\_tables",\
Add custom field "Total Amount ￥" \|
