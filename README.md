## How to integrate Zendesk into your Android Application

- put the zendesk.jar into a "lib" folder underneath the root directory of your Android project


- Ensure the application has permission to access the network by adding the following to your manifest

  ``<uses-permission android:name="android.permission.INTERNET"></uses-permission>``


- Configure the endpoint (the domain you use to log into zendesk) in the manifest, replacing "yoursubdomain" in the text below

    ``<meta-data android:name="zendesk_url" android:value="yoursubdomain.zendesk.com"/>``

- Configure the title used in the helpdesk dialog

    ``<meta-data android:name="zendesk_title" android:value="Your Title"/>``	

  *Note: both <meta-data> tags need to be inside the <application> tag.

- Invoke the builder and create the dialog by inserting the following code (usually in your onCreateDialog method of your Activity).

	``ZendeskDialog.Builder(this).create().show();``

- Optionally you can override the default description text in the dialog from within the manifest

    ``<meta-data android:name="zendesk_description" android:value="How may we help you?"/>``

- Optionally specify the tag for tickets (the default is dropbox)

    ``<meta-data android:name="zendesk_tag" android:value="dropbox"/>``

- Optionally you can configure everything programatically using the Dialog Builder style API

    ```
    ZendeskDialog.Builder(this)
    	.setTitle("custom title")
    	.setDescription("custom description")
    	.setUrl("subdomain.zendesk.com")
    	.setTag("dropbox")
    ```

## Copyright and license

Copyright 2013 Zendesk

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
        .create();
