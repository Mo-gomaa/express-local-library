## Express tutorial by MDN that aims to learn about node and how do databases with servers and send data to client.

### This project has three stages to finish:

1.  Finish the hands-on Tutorial first
2.  Work through the challenge yourself section in the end that implements other https methods like
    POST, UPDATE, DELETE

    Implement the delete pages for the Book, BookInstance, and Genre models,
    linking them from the associated detail pages in the same way as our Author delete page.
    The pages should follow the same design approach:

         - If there are references to the object from other objects,
           then these other objects should be displayed along with a note that this record
           can't be deleted until the listed objects have been deleted.

The thought process:

The relations:
in order to approach this problem, you need to know the relations:
Every author has one or more books but every book only has one author.
Every book has zero or more book instances but every book instance has only one book
Every book has zero or more genres and every genre has zero or more books.

         - If there are no other references to the object then the
           view should prompt to delete it. If the user presses the Delete button,
           the record should then be deleted.

In order to implement the delete process of any of the objects you need to determine what references
will be depended on before deletion.
To delete:
An author, you need to check it has no books

A book, you need to check it has no bookinstances

A genre, you need to check it has no books

A bookinstance, you need to check nothing
A few tips:

         - Deleting a Genre is just like deleting an Author,
           as both objects are dependencies of Book (so in both cases you
           can delete the object only when the associated books are deleted).

         - Deleting a Book is also similar as you need to first check that there are no
           associated BookInstances.

         - Deleting a BookInstance is the easiest of all because there are no
           dependent objects. In this case, you can just find the associated record and delete it.

    Implement the update pages for the BookInstance, Author, and Genre models,
    linking them from the associated detail pages in the same way as our Book update page.
    A few tips:

         - The Book update page we just implemented is the hardest! The same patterns can be
           used for the update pages for the other objects.

         - The Author date of death and date of birth fields and the BookInstance due_date field
           are the wrong format to input into the date input field on the form (it requires data
           in form "YYYY-MM-DD"). The easiest way to get around this is to define
           a new virtual property for the dates that formats the dates appropriately,
           and then use this field in the associated view templates.

         - If you get stuck, there are examples of the update pages in the
           [example here]https://github.com/mdn/express-locallibrary-tutorial

3.  Deployment to production
