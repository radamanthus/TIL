# Start a new Rails+React project

_Mini Project: Automate all or some of these using a Rails Application Template: https://edgeguides.rubyonrails.org/rails_application_templates.html_

From: [react-rails README](https://github.com/reactjs/react-rails)

Create a new Rails application

```
rails new my-app
cd my-app
```

Add the gems to the Gemfile:

```
gem 'webpacker'
gem 'react-rails'
```

Run the installers

```
bundle install
rails webpacker:install
rails webpacker:install:react
rails generate react:install
```

Link the JavaScript pack using the `javascript_pack_tag` helper. Add this to `application.html.erb` or to a specific layout:

```
<%= javascript_pack_tag 'application' %>
```

Generate a React component:

```
rails g react:component HelloWorld greeting:string
```

Render the component in a Rails view:

```
<%= react_component("HelloWorld", { greeting: "Hello from react-rails." }) %>
```

Add the Semantic UI CSS to `application.html.erb` or a specific layout:

```
<%= stylesheet_link_tag    'application', "https://cdn.jsdelivr.net/npm/semantic-ui@2.4.2/dist/semantic.min.css" %>
```
