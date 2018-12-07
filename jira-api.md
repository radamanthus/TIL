# JIRA API

### Play with the JQL

Generate an API token here: https://confluence.atlassian.com/cloud/api-tokens-938839638.html

Base64 encode <your_username>:<your_token>

```
function buildJqlBody(project, time_window, max_results) {
  return {
    'jql':`created>-${time_window} AND project=${project}`,
    'startAt': 0,
    'maxResults': max_results
  };
}

var jira = new JiraClient( {
  host: 'myohstname.net',
  basic_auth: {
    base64: '<redacted>' // base64 encoding of myemail@mydomain.com:my_api_token
  }
});

jira.search.search(buildJqlBody('TG', '4h', 42), function(error, issues) {
  console.log(issues);
});

```
