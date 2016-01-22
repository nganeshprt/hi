<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Contact Manager</title>
    <link href="vendor/bootstrap/dist/css/bootstrap.css" rel="stylesheet">
    <link href="app/css/main.css" rel="stylesheet">
  </head>
  <body>
    <header class="bs-header">
      <div class="container">
        <h1>My Buddies Contact List</h1>
        <p>Backbone Application Done By Ganesh Vignesh  Karthik</p>
      </div>
    </header>
    <div class="container">
      <div class="row">
        <div class="col-xs-12 main-container">
        </div>
      </div>
    </div>

    <script type="text/template" id="tpl-contacts">
      <h2 class="page-header text-center">List of Buddies</h2>
      <p class="text-center">
        <a href="#contacts/new" class="btn btn-lg btn-outline">Add Contact</a>
      </p>
      <ul class="media-list row contacts-container"></ul>
    </script>

    <script type="text/template" id="tpl-contact">
      <div class="thumbnail">
        <img class="media-object" src="app/img/faces/<%- avatar %>">
      </div>
      <div class="media-heading">
        <h3>
          <%- name %>
          <small>
            <a href="#contacts/edit/<%- id %>"><span class="glyphicon glyphicon-pencil"></span></a>
            <a href="#contacts/delete/<%- id %>" class="delete-contract">
              <span class="glyphicon glyphicon-trash"></span>
            </a>
          </small>
        </h3>
      </div>
      <div class="media-body">
        <dl>
          <dt>Phone Number:</dt>
          <dd><%- tel %></dd>
          <dt>Email:</dt>
          <dd><%- email %></dd>
        </dl>
      </div>
      <hr>
    </script>

    <script type="text/template" id="tpl-new-contact">
      <h2 class="page-header text-center"><%= isNew ? 'Create' : 'Edit' %> Contact</h2>
      <form role="form" class="form-horizontal contract-form">
        <div class="form-group">
          <label class="col-sm-4 control-label">Full name:</label>
          <div class="col-sm-6">
            <input type="text" class="form-control contact-name-input" value="<%- name %>">
          </div>
        </div>
        <div class="form-group">
          <label class="col-sm-4 control-label">Email address:</label>
          <div class="col-sm-6">
            <input type="email" class="form-control contact-email-input" value="<%- email %>">
          </div>
        </div>
        <div class="form-group">
          <label class="col-sm-4 control-label">Telephone number:</label>
          <div class="col-sm-6">
            <input type="tel" class="form-control contact-tel-input" value="<%- tel %>">
          </div>
        </div>
        <div class="form-group">
          <div class="col-sm-offset-4 col-sm-3">
            <button type="submit" class="btn btn-outline btn-lg btn-block">Submit</button>
          </div>
          <div class="col-sm-3">
            <a href="#contacts" class="btn btn-outline btn-lg btn-block">Cancel</a>
          </div>
        </div>
      </form>
    </script>

    <script src="vendor/jquery/jquery.js"></script>
    <script src="vendor/underscore/underscore.js"></script>
    <script src="vendor/backbone/backbone.js"></script>

    <script src="app/js/app.js"></script>
    <script src="app/js/models/contacts.js"></script>
    <script src="app/js/collections/contacts.js"></script>
    <script src="app/js/views/contact.js"></script>
    <script src="app/js/views/contacts.js"></script>
    <script src="app/js/views/contactForm.js"></script>
    <script src="app/js/router.js"></script>

    <script>
      $(function() {
        ContactManager.start({
          contacts: [
            {
              id: 1,
              name : 'GANESH',
              tel: '8122898926',
              email: 'nganeshm1988@gmail.com'
            },
            {
              id: 2,
              name : 'vignesh',
              tel: '9876568897',
              email: 'csevickee@gmail.com'
            },
            {
              id: 3,
              name : 'Karthik',
              tel: '9198234576',
              email: 'karthik@gmail.com'
            },
            {
              id: 4,
              name : 'Visu',
              tel: '7029895145',
              email: 'visu@outlook.com'
            },
            {
              id: 5,
              name : 'Ramanathan',
              tel: '9488767345',
              email: 'ram@yahoo.com'
            },
            {
              id: 6,
              name : 'jagdeesh',
              tel: '8035579815',
              email: 'jaggu@live.in'
            }
          ]
        });
      });
    </script>
  </body>
</html>
