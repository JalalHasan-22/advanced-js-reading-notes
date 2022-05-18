# Reading: <Login /> and <Auth />

## What is Role-based Access Control ?

Role-based access control (RBAC) restricts network access based on a person's role within an organization and has become one of the main methods for advanced access control. The roles in RBAC refer to the levels of access that employees have to the network.

Employees are only allowed to access the information necessary to effectively perform their job duties. Access can be based on several factors, such as authority, responsibility, and job competency. In addition, access to computer resources can be limited to specific tasks such as the ability to view, create, or modify a file.

As a result, lower-level employees usually do not have access to sensitive data if they do not need it to fulfill their responsibilities. This is especially helpful if you have many employees and use third-parties and contractors that make it difficult to closely monitor network access. Using RBAC will help in securing your company’s sensitive data and important applications.

### BENEFITS OF RBAC

Managing and auditing network access is essential to information security. Access can and should be granted on a need-to-know basis. With hundreds or thousands of employees, security is more easily maintained by limiting unnecessary access to sensitive information based on each user’s established role within the organization. Other advantages include:

Reducing administrative work and IT support. With RBAC, you can reduce the need for paperwork and password changes when an employee is hired or changes their role. Instead, you can use RBAC to add and switch roles quickly and implement them globally across operating systems, platforms and applications. It also reduces the potential for error when assigning user permissions. This reduction in time spent on administrative tasks is just one of several economic benefits of RBAC. RBAC also helps to more easily integrate third-party users into your network by giving them pre-defined roles.
Maximizing operational efficiency. RBAC offers a streamlined approach that is logical in definition. Instead of trying to administer lower-level access control, all the roles can be aligned with the organizational structure of the business and users can do their jobs more efficiently and autonomously.
Improving compliance. All organizations are subject to federal, state and local regulations. With an RBAC system in place, companies can more easily meet statutory and regulatory requirements for privacy and confidentiality as IT departments and executives have the ability to manage how data is being accessed and used. This is especially significant for health care and financial institutions, which manage lots of sensitive data such as PHI and PCI data.

## React-cookies Component

Cookies are the data stored in the form of key-value pairs that are used to store information about the user on their computer by the websites that the users browse and use it to verify them. To set or remove the cookies, we are going to use a third-party dependency of react-cookie.

first, this library can be installed by running the following code in the consol:

> $ npm install react-cookies

### setting a coookie in React

Firstly, import the CookiesProvider component from the react-cookie package and wrap the index.js or the root app component of your application with the CookiesProvider component from the react-cookie package.

> import { CookiesProvider } from "react-cookie";<br>
> import App from "./App";<br>
> const rootElement = document.getElementById("root");<br>
> ReactDOM.render(<br> \<CookiesProvider><br> > \<App /><br> \</CookiesProvider>,<br>
> rootElement<br>
> );

After that use the useCookies hook provided by it which has a syntax of −

> const [cookies, setCookie, removeCookie] = useCookies(['cookie-name']);

Now, inside your React component, you can access the cookie by using a useCookies() hook.

> const [cookies, setCookie] = useCookies();
