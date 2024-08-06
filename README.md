# Token Mfa
  
Personal access tokens are intended to access GitHub resources on behalf of yourself. To access resources on behalf of an organization, or for long-lived integrations, you should use a GitHub App. For more information, see "About creating GitHub Apps."
 
**DOWNLOAD ⚙⚙⚙ [https://stupimoplanze.blogspot.com/?download=2A0Tbz](https://stupimoplanze.blogspot.com/?download=2A0Tbz)**


 
GitHub currently supports two types of personal access tokens: fine-grained personal access tokens and personal access tokens (classic). GitHub recommends that you use fine-grained personal access tokens instead of personal access tokens (classic) whenever possible.
 
Organization owners can set a policy to restrict the access of personal access tokens (classic) to their organization. For more information, see "Setting a personal access token policy for your organization."

If you choose to use a personal access token (classic), keep in mind that it will grant access to all repositories within the organizations that you have access to, as well as all personal repositories in your personal account.
 
As a security precaution, GitHub automatically removes personal access tokens that haven't been used in a year. To provide additional security, we highly recommend adding an expiration to your personal access tokens.
 
Personal access tokens are like passwords, and they share the same inherent security risks. Before creating a new personal access token, consider if there is a more secure method of authentication available to you:
 
When using a personal access token in a script, you can store your token as a secret and run your script through GitHub Actions. For more information, see "Using secrets in GitHub Actions." You can also store your token as a Codespaces secret and run your script in Codespaces. For more information, see "Managing your account-specific secrets for GitHub Codespaces."
 
Under **Resource owner**, select a resource owner. The token will only be able to access resources owned by the selected resource owner. Organizations that you are a member of will not appear unless the organization opted in to fine-grained personal access tokens. For more information, see "Setting a personal access token policy for your organization."
 
Under **Repository access**, select which repositories you want the token to access. You should choose the minimal repository access that meets your needs. Tokens always include read-only access to all public repositories on GitHub.
 
Under **Permissions**, select which permissions to grant the token. Depending on which resource owner and which repository access you specified, there are repository, organization, and account permissions. You should choose the minimal permissions necessary for your needs.
 
The REST API reference document for each endpoint states whether the endpoint works with fine-grained personal access tokens and states what permissions are required in order for the token to use the endpoint. Some endpoints may require multiple permissions, and some endpoints may require one of multiple permissions. For an overview of which REST API endpoints a fine-grained personal access token can access with each permission, see "Permissions required for fine-grained personal access tokens."
 
If you selected an organization as the resource owner and the organization requires approval for fine-grained personal access tokens, then your token will be marked as pending until it is reviewed by an organization administrator. Your token will only be able to read public resources until it is approved. If you are an owner of the organization, your request is automatically approved. For more information, see "Reviewing and revoking personal access tokens in your organization."
 
**Note**: Organization owners can restrict the access of personal access token (classic) to their organization. If you try to use a personal access token (classic) to access resources in an organization that has disabled personal access token (classic) access, your request will fail with a 403 response. Instead, you must use a GitHub App, OAuth app, or fine-grained personal access token.
 
**Note**: Your personal access token (classic) can access every repository that you can access. GitHub recommends that you use fine-grained personal access tokens instead, which you can restrict to specific repositories. Fine-grained personal access tokens also enable you to specify fine-grained permissions instead of broad scopes.
 
Select the scopes you'd like to grant this token. To use your token to access repositories from the command line, select **repo**. A token with no assigned scopes can only access public information. For more information, see "Scopes for OAuth apps."
 
To use your token to access resources owned by an organization that uses SAML single sign-on, authorize the token. For more information, see "Authorizing a personal access token for use with SAML single sign-on" in the GitHub Enterprise Cloud documentation.
 
For example, to clone a repository on the command line you would enter the following git clone command. You would then be prompted to enter your username and password. When prompted for your password, enter your personal access token instead of a password.
 
Instead of manually entering your personal access token for every HTTPS Git operation, you can cache your personal access token with a Git client. Git will temporarily store your credentials in memory until an expiry interval has passed. You can also store the token in a plain text file that Git can read before every request. For more information, see "Caching your GitHub credentials in Git."
 
i am using some of the http api endpoints to upload or download files. As i saw in the documentation the API access tokens never expire but can only be revoked. For some reason after i use my token for a day or so i get the message "expired\_access\_token". Then i need to create a new one. Of course i never revoked it manually or from the api.
 
I have another account where there i don't have any issue. My token is still working after many months. I followed the same process to create both of them but still they are different. The token for my old account is 64 characters long but the new one is 139 and always starts with "sl.".
 
Based on your description, it sounds like you're getting the access token from the "API v2 Explorer". That tool is just meant for prototyping Dropbox API calls, and currently has early access to an upcoming "short-lived access token" feature. That means that, unlike standard Dropbox API access tokens, the access tokens you get from the API Explorer will expire by themselves. (You can identify them by the "sl." prefix you mentioned.)
 
To get standard Dropbox API access tokens, you should use your own API app registration. For instance, you can use the "Generate" button on your app's page on the App Console, or use the OAuth app authorization flow with your app.
 
Thank you very much for taking the time to answer. I tested like an hour ago to create my app and generate token for my app and its working as expected. The token generated is shorter and does not have the prefix "sl". Its the same format as the token i created in the past through the API Explorer. It was my fault to use the token from the API explorer for my requests. Anyway, thanks again for your help!
 
@SerenityNow Dropbox is no longer offering the option for creating new long-lived access tokens. Dropbox is now issuing short-lived access tokens (and optional refresh tokens) instead of long-lived access tokens. You can find more information on this migration here.

Apps can still get long-term access by requesting "offline" access though, in which case the app receives a "refresh token" that can be used to retrieve new short-lived access tokens as needed, without further manual user intervention. Refresh tokens do not expire automatically and can be used repeatedly. You can find more information in the OAuth Guide and authorization documentation. There's a basic outline of processing this flow in this blog post which may serve as a useful example.
 
So I wanted to make a windows maintenance bot that I could sell to my friends, but I didn't want to have to copy the files for each person. So I thought I would make an improvised install and update executable. My plan was to upload the bot files to a private dropbox account that the bot would have access to. Then the small install executable would just download the files to their computer from dropbox, along with an update routine that will detect if there has been a change to the files stored, and update their local bot files.
 
I can download and detect changes just fine, but my access token keeps expiring. I researched for a bit and found that there was an option to make the token not expire, and then researched a bit more and found that you guys removed the feature. I've been researching for hours and I have no idea how to make the bot have permanent access to the private drop box account. Can you help me out? Also, forgot to mention I'm using the JS api.
 
Dropbox is currently in the process of switching to only issuing short-lived access tokens (and optional refresh tokens) instead of long-lived access tokens. You can find more information on this migration here.

Apps can still get long-term access by requesting "offline" access though, in which case the app receives a "refresh token" that can be used to retrieve new short-lived access tokens as needed, without further manual user intervention. You can find more information in the OAuth Guide and authorization documentation.
 a2f82b0cb4
 
