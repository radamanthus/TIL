# Start a new Rails+React project

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
