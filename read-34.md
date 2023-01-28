# API Deployment

This topic matters as it relates to learning best practices for API Deployment in Python. 

---

### Django Settings Best Practices

The settings file is a very important part of our Django projects. If we do it wrong, we’ll have a lot of issues during all phases of development. But if we do it right, it will be a good basis for our project that will allow it to grow and scale in the future.

Using the environment variables approach, we can easily switch from a monolith to microservice architecture, wrap our project in Docker containers, and deploy it in any VPS or Cloud hosting platform such as: Amazon, Google Cloud, or your own Kubernetes cluster.

#### Managing Django Settings: Issues

* **Different environments -** Each environment can have its own specific settings. (e.g.) DEBUG = True, more verbose logging, additional apps, etc.
* **Sensitive data -** SECRET_KEY in each Django project. DB passwords and tokens for third-party APIs. This data cannot be stored in VCS.
* **Sharing settings between team members -** Need a general approach to eliminate human error when working with the settings.
* **Django settings are a Python code -** It gives us a lot of flexibility, but can also be a problem – instead of key-value pairs, settings.py can have a very tricky logic.

#### Setting Django Configurations: Different Approaches

##### settings_local.py

* Pros:
  * Secrets not in VCS.
* Cons:
  * settings_local.py is not in VCS. Can lose some of our environment settings.
  * The Django settings file is a Python code. Can have some non-obvious logic.
  * Need to have settings_local.example (in VCS) to share the default Django configurations for developers.

##### Separate settings file for each environment

* Pros:
  * All environments are in VCS.
  * Easy to share settings between developers.
* Cons:
  * Need to find a way to handle secret passwords and tokens.
  * Inheritance of settings can be hard to trace and maintain.

##### Environment variables

* Pros:
  * Django config is separated from code. 
  * Environment parity – We have the same code for all environments. 
  * No inheritance in settings. Cleaner and more consistent code. 
  * There is a theoretical grounding for using Django environment variables – 12 Factors. 
* Cons:
  * Need to handle sharing default config between developers.

#### 12 Factors

* Codebase
* Dependencies
* Config
* Backing services
* Build, release, run
* Processes
* Port binding
* Concurrency
* Disposability
* Dev/prod parity
* Logs
* Admin processes

#### Best practices

* Keep settings in environment variables.
* Write default values for production configuration (excluding secret keys and tokens). 
* Don’t hardcode sensitive settings. Don’t put them in VCS. 
* Split settings into groups: Django, third-party, project. 
* Follow naming conventions for custom (project) settings.

[*source*](https://djangostars.com/blog/configuring-django-settings-best-practices/)

---

### SSH Tutorial

#### What Is SSH?

SSH (Secure Shell Protocol) is a remote administration protocol that allows users to access, control, and modify their remote servers over the internet. Gaining an in-depth understanding of the underlying how SSH works can help users understand the security aspects of this technology.

#### Symmetric Encryption

Symmetric encryption is a form of encryption where a secret key is used for both encryption and decryption of a message by both the client and the host. Anyone with the key can decrypt the message being transferred.

#### Asymmetric Encryption

Asymmetrical encryption uses two separate keys for encryption and decryption. These two keys are known as the public key and the private key. Both these keys form a public-private key pair.

#### Hashing

One-way hashing is another form of cryptography used in Secure Shell Connections. One-way-hash functions differ from the above two forms of encryption in the sense that they are never meant to be decrypted. They generate a unique value of a fixed length for each input that shows no clear trend which can be exploited. This makes them practically impossible to reverse.

#### Authenticating the User

For authenticating user credentials, we use a password. The user is asked to enter the username, followed by the password. These credentials securely pass through the symmetrically encrypted tunnel, so there is no chance of them being captured by a third party. It is still not recommended to use passwords for secure connections. This is because many bots can simply brute force easy or default passwords and gain access to your account. Instead, the recommended alternative is SSH Key Pairs.

[*source*](https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work)

### Things I want to know more about

* I would like to know more about the underlying security aspects of the SSH technology.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
