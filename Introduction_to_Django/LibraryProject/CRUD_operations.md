from bookshelf.models import Book

book = Book.objects.create(title="1984", author="George Orwell", publication_year=1949)
book
# <Book: 1984 by George Orwell (1949)>

Book.objects.all()
# <QuerySet [<Book: 1984 by George Orwell (1949)>]>
book = Book.objects.get(title="1984")
book.title = "Nineteen Eighty-Four"
book.save()
book
# <Book: Nineteen Eighty-Four by George Orwell (1949)>
book = Book.objects.get(title="Nineteen Eighty-Four")
book.delete()
# (1, {'bookshelf.Book': 1})

Book.objects.all()
# <QuerySet []>
