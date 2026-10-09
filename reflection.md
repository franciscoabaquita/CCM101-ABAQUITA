# Mission Reflection

> **Draft for personalization:** This reflection is a starting point. Update the personal reactions and Mission 1 comparison so they accurately describe your own experience before submitting.

Writing a `docker-compose.yml` file makes deployment easier because it records the services, images, ports, and settings in one readable place. Instead of remembering and retyping several long commands, an engineer can review the configuration, share it with teammates, and use the same instructions to recreate the stack. This is a practical example of Infrastructure as Code: the desired setup is described declaratively and can be version-controlled.

YAML indentation defines the structure of the configuration. A misplaced space or a tab can make the file invalid or attach a setting to the wrong service. Docker Compose may report a parsing error, so consistent spaces and checking the file before deployment are important.

Environment variables provide the settings the containers need, including database name, username, password, and host. They let the application and database be configured consistently without baking those values into application code. The sample uses simple demonstration passwords; a real deployment should use stronger credentials and keep secrets out of version control.

Deploying Nextcloud with a database in a few minutes demonstrates how much work automation can simplify. The experience can make a multi-container application feel more approachable: one configuration describes how the components fit together, and a small set of commands starts or removes them. The setup screen also makes the result tangible because it shows that the web tier is responding.

Compared with Mission 1, this lab can show a shift from thinking about cloud computing as only individual servers or services toward seeing it as a coordinated system. A cloud engineer must consider how components communicate, where persistent data belongs, how configuration is repeated reliably, and how the whole deployment is documented. These habits make it easier to maintain and troubleshoot infrastructure as it grows.

**Word count:** 289
