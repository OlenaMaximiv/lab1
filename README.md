# lab1
Maksymiv Olena. IH.M-22

Web app for testing

Updated version for unubtu.

Source: https://github.com/Fluffy777/universe

Introduction
This project is a Java-based application built with the Javalin framework. Its primary goal is to provide a platform for users to create their own world by sharing their thoughts, experiences, and impressions with their audience. With this blog, users can share their ideas with the world and connect with others who share similar interests.

Features
User authentication: users can sign up, sign in, and sign out securely.
Password recovery: users can reset their password if they forget it.
Account management: users can edit their account information.
Create and publish posts: users can write and publish posts on their own blog.
Leave comments: users can comment on posts and interact with other readers.
View posts and comments: users can view their own posts, comments, as well as other users' posts and comments.

Prerequisites
To build and run this project, you will need:

Java 17+
Maven
SQLite
Make and its dependencies (optional, but recommended for an optimized development workflow)
MailHog (required if you want to test email functionality locally. Otherwise, you can modify the run properties to use a public SMTP server)
Your next step will be to follow these instructions:

Download Java 17 (or newer) zip-archive from the provided link and extract it to a location of your choice.
If you are not using a bundled version of Maven from an IDE like IntelliJ IDEA, download the Maven zip-archive and extract it to a location of your choice as well.
SQLite command line tool called sqlite3.exe is already included in the project files folder, so you don't need to install it separately.
If you want to optimize your development workflow, you can install Make with its dependencies for Windows. To do this, download the Make zip-archive and extract the bin folder with the make.exe program. Place the dependencies (such as libintl3.dll and libiconv2.dll) in the same folder.
Modify your Path system environment variable to include the paths to the bin folders for Java, Maven, SQLite, and Make (if installed). Make sure the paths include the bin folder name.
MailHog doesn't require installation as it is a standalone local SMTP server. You can simply place the executable file wherever you prefer.
Installation
Download or clone the project repository to your local machine using git clone https://github.com/Fluffy777/universe.git . (where . will be your current folder).
Open a command shell from the root folder of the project.
Run the following command to generate an SQLite database in the project folder: make migrate
Build the project by running the following command: make
Configuration
To configure the web application, edit the parameter values in a .properties file. By default, the file is called application.properties if you use the make tool. Otherwise, you can name it anything and specify it as a call argument. You can also use environment variables. The settings of the application's aspects, including the embedded Jetty web server properties, mailing configuration, security strength, and database connection details, are determined by their usage. The project repository has a file with default values set, which you can use. For more flexibility, refer to the table below.

Key	Value
application.host	The IP address to which the application should bind
application.port	The port on which the application should run
application.bcryptStrength	The strength of the bcrypt encryption algorithm
database.filename	The path to the SQLite database in either absolute or relative form
mail.from	The email address of the sender of the email
mail.user	The identifier of the sender of the email on SMTP server
mail.password	The credential that is used to authenticate the email sender on SMTP server
mail.host	The IP address to which the SMTP server should bind
mail.port	The port on which the SMTP server should run
mail.ssl	Determines whether to use SSL encryption or not
mail.auth	Determines whether or not the email sender should be authenticated on the SMTP server
Run
If you prefer to use a local SMTP server, run MailHog. Note that the default host is set to 0.0.0.0, which means "localhost" in the context of this program. The default ports are 1025 for SMTP connections and 8025 for HTTP connections, which provide a useful web interface for email management.
Start the application by running the following command from the command shell: make run
That's it! The application should be up and running now, and you can access it at the specified port and URL in your web browser.
