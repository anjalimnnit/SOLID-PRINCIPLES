# SRP

When we are writing longer codes we do need to consider
the fact that our code should be maintainable.
If we write too much functionalities in a single class it becomes the God class.
And it is difficult to add features or modify the God class.
Therefore the class must have only a single responsibility
or a single reason to change.
Here is a simple example to explain this:

Let us take an example of shopping site.
Suppose we have an user trying to login to a website.
These are the possibilities :

interface IUser
{
boolean Login(string userName, string password);
boolean Register(string userName, string password, string email);
void LogError(string msg);
boolean sendMail(string content);
}

But here we can find that login or Register is handled by user
and rest two can be separated from them.
After applying SRP
interface IUser
{
boolean Login(string userName, string password);
boolean Register(string userName, string password, string email);
}

interface IError
{
void LogError(string msg);
}

interface IEmail
{
boolean sendMail(string content);
}