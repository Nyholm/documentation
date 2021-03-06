
.. code-block:: bash

 curl -s --user 'api:YOUR_API_KEY' -X DELETE \
     https://api.mailgun.net/v2/YOUR_DOMAIN_NAME/mailboxes/alice

.. code-block:: java

 public static ClientResponse DeleteMailbox() {
 	Client client = Client.create();
 	client.addFilter(new HTTPBasicAuthFilter("api",
 			"YOUR_API_KEY"));
 	WebResource webResource =
 		client.resource("https://api.mailgun.net/v2/YOUR_DOMAIN_NAME" +
 				"/mailboxes/alice");
 	return webResource.delete(ClientResponse.class);
 }

.. code-block:: php

  # Include the Autoloader (see "Libraries" for install instructions)
  require 'vendor/autoload.php';
  use Mailgun\Mailgun;

  # Instantiate the client.
  $mgClient = new Mailgun('YOUR_API_KEY');
  $domain = 'YOUR_DOMAIN_NAME';
  $mailbox = 'alice';

  # Issue the call to the client.
  $result = $mgClient->delete("$domain/mailboxes/$mailbox");

.. code-block:: py

 def delete_mailbox():
     return requests.delete(
         "https://api.mailgun.net/v2/YOUR_DOMAIN_NAME/mailboxes/alice",
         auth=("api", "YOUR_API_KEY"))

.. code-block:: rb

 def delete_mailbox
   RestClient.delete "https://api:YOUR_API_KEY"\
   "@api.mailgun.net/v2/YOUR_DOMAIN_NAME/mailboxes/alice"
 end

.. code-block:: csharp

 public static IRestResponse DeleteMailbox() {
 	RestClient client = new RestClient();
 	client.BaseUrl = "https://api.mailgun.net/v2";
 	client.Authenticator =
 		new HttpBasicAuthenticator("api",
 		                           "YOUR_API_KEY");
 	RestRequest request = new RestRequest();
 	request.AddParameter("domain",
 	                     "YOUR_DOMAIN_NAME", ParameterType.UrlSegment);
 	request.Resource = "{domain}/mailboxes/{username}";
 	request.AddUrlSegment("username", "alice");
 	request.Method = Method.DELETE;
 	return client.Execute(request);
 }

.. code-block:: go

 // coming soon
