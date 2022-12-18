# Shrtnr UI

The UI component of the system will be the principle method for users to interact with the system.

Users will register and be authenticated by the [OIDC system](./shrtnr-oidc.md). From here they will be able to shorten their URLs and view analytics build from the [analytics service](./shrtnr-analytics.md).

## Propposed Tech

A UX/UI designer can spec out the application.

Using the modern [material](https://m3.material.io/) design paradigm comes recommended.

Being a web front end the following technologies will be useful:

- [React](https://reactjs.org/docs/getting-started.html):
    - Very quick to bootstrap and hit the ground running
    - Popular framework with lots of developers
    - Can be set up to have useful tools like tests, typescript etc.

- [Angular](https://angular.io/docs):
    - Comes full features out of the box and is ideal for enterprise scale development.
    - Uses typescript natively and provides a lot more robust compilation safety.
    - Has a heavier learning curve than most front-end frameworks.
