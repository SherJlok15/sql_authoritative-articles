# Authoritative articles

1. Using your favorite DB client, design and create a table called `authors` that would store the first name, the last name, and the sex of each of the following authors:

      - Abi Maxwell (F)
      - Anthony Alofsin (M)
      - Emily Temple (F)
      - Gabrielle Bellot (F)
      - Meg Donohue (F)
      - Philip Eil (M)
      - Roxana Robinson (F)
      - Tobias Carroll (M)
      - Veronica Esposito (F)

    Don’t forget that each table must have an ID field. Please also create the necessary constraints, keys and/or indices for the table. In order to do this you might first need to read this document through the end.

    Copy and paste the SQL query generated by the client below:

    ```postgresql
    create table author
    (
    	id int
    		constraint author_pk
    			primary key,
    	first_name text not null,
    	last_name text not null,
    	sex text
    );


    ```

2. **Manually** create a query or a series of queries filling the table with the data. Put the query/queries below:

    ```postgresql
    INSERT INTO authors ("first_name", "last_name", sex)
    VALUES ('Abi', 'Maxwell', 'F'),
           ('Anthony', 'Alofsin', 'M'),
           ('Emily', 'Temple', 'F'),
           ('Gabrielle', 'Bellot', 'F'),
           ('Meg', 'Donohue', 'F'),
           ('Philip', 'Eil', 'M'),
           ('Roxana', 'Robinson', 'F'),
           ('Tobias', 'Carroll', 'M'),
           ('Veronica', 'Esposito', 'F');
    ```

3. Using the client, design and create a table called `articles` that would store the information from the file [articles.xlsx](articles.xlsx). Use the already created `authors` table in order to refer to the authors. Don’t forget to create an ID field and all necessary constraints/keys/indices.

    Copy and paste the SQL query generated by the client below:

    ```postgresql
    create table articles
    (
    	id serial
    		constraint articles_pk
    			primary key,
    	title text,
    	author text,
    	date date,
    	rating double precision,
    	text text
    );


    ```

4. **Using the client**, fill the table:

    ```postgresql
    INSERT INTO articles (title, author, date, rating, text)
    VALUES ('How Alison Bechdel Understands Her Life as Fiction',
            'Gabrielle Bellot', '2017-10-04', 4.30, '<p>A third of the way through her seminal autobiographical graphic novel, Fun Home, Alison Bechdel reveals the reasons for the many literary allusions—Henry James, Fitzgerald, Camus, Greek mythology—peppered throughout the book. “I employ these allusions,” she writes, “not only as descriptive devices, but because my parents are most real to me in fictional terms. And perhaps,” she reflects, “my cool aesthetic distance itself does more to convey the arctic climate of our family than any particular literary comparison.” Not long before this, Bechdel has not only come out as a lesbian but learned, too, that her father had a disquieting secret passion for underage boys—but it was this revelation about her allusions, more than anything else, that made me pause in my rereading of her intricate masterpiece. Fiction, it seemed, was the best translator of the curious language of her life; here was an autobiography that would have been impossible without fiction.</p>'),
           ('How Jamaica Kincaid Helped Me Understand My Mother',
            'Gabrielle Bellot', '2019-03-22', 3.35, '<p>For two decades, my mother told me stories about going to a convent in Grenada. “It was where I learnt manners,” she would say, smiling. Her own mother, a grand woman from Curaçao who had married a Dominican man during the shipwreck chaos of the Second World War and moved with him to that legendarily green island in the middle of the Caribbean, had sent her 13 daughters to the convent of St. Joseph of Cluny, where the nuns taught them the indelible arts of propriety. They were punished if they did not wear their uniforms correctly, arrange their napkins in napkin holders the right way, or finish each grain of rice on their plates; one of my aunties wailed all night in front of an insurmountable plate of food, until she fell asleep at the table.</p>'),
           ('How Many Copies Did Famous Books Sell in the First Year?',
            'Emily Temple', '2019-06-25', 2.40, '<p>Book publishing can be a tricky—and fickle—thing. Some of the classics we know and love today were instant bestsellers when they were originally published—and some were huge flops. While the numbers a book puts up during its first year in the world aren’t everything, they can be fascinating—especially when they’re a lot lower (or higher) than you’d think. (I mean, just look at Joyce.) So to that end, I’ve hunted around to find out how many copies the below books sold in the twelve months following their publications. Obviously, most of the numbers are approximate (it’s pretty clear when they’re not), and of course I haven’t mentioned every book on on the spectrum (because that would just be . . . every book). But if you’re a writer who knows your own book’s numbers, and you’re brave, feel free to add to the list in the comments section.</p>'),
           ('My Decade-Long Fascination with the Tale of Monica Lewinsky',
            'Gabrielle Bellot', '2019-05-29', 5.00, '<p>For over a decade now, I’ve maintained a fascination with Monica Lewinsky so ardent that it borders on obsession. It began during my senior year of college, when I took a literature seminar that focused on early sentimental novels about scorned women. The course culminated in a research paper on a woman from history whose sexual decisions led to her to be scandalized by her society.</p>'),
           ('On “Good Men” and the Vague, Low Standards Required to Be One',
            'Abi Maxwell', '2018-04-29', 4.50, '<p>The first time I fell in love, I was 14 years old, working nights and weekends as a ski instructor at the local mountain that had one chairlift and one rope tow. He also worked there, and he didn’t love me back—or at least I hope he didn’t; he was 25. Saying it now, as an adult, feels horrifying, though for years I stood firm that he was a good man and there was nothing particularly sinister about the relationship. He picked me up on the way to the mountain, and drove me home at night. We never actually had lessons to teach, so we spent our time riding the chairlift and skiing together. Sometimes, we would talk on the phone. He even made me a mix tape.</p>'),
           ('On Frank Lloyd Wright and the Architectural War For New York’s Skyline',
            'Anthony Alofsin', '2019-02-01', 3.85, '<p>The New York City to which Frank Lloyd Wright returned in late 1926 was dramatically different from the metropolis he had encountered in 1909, but its evolution was not a mystery. The dramatic skyscrapers, the stock market, airplanes, jazz, the Harlem Renaissance, radio, and even organized crime, which gave the 1920s their fame, did not appear from nowhere. All had developed from the preceding decades. The risk was large, but for greater New York, still barely 20 years old, “the ties that bound—subways, bridges, schools, amusement parks, police, theaters, jobs, water, public health, Tammany, the excitement and pride of living in a great city—overmatched the innumerable antagonisms and kept them with bounds.” Squinting at risk, its citizens might assume “so far so good.”</p>'),
           ('On the Modern American Obsession with French Revolution Narratives',
            'Tobias Carroll', '2019-05-03', 4.00, '<p>Will we ever run out of stories to tell about the French Revolution? Edward Carey’s recent novel Little is the second novel in a decade to examine that period through the eyes of Marie Grosholtz, better known as Madame Tussaud; it’s preceded by Michelle Moran’s Madame Tussaud: A Novel of the French Revolution. Before Hilary Mantel chronicled the palace intrigue surrounding Henry VIII and Thomas Cromwell, she explored intrigue among revolutionaries in her novel A Place of Greater Safety. And Emma Orczy’s 1905 novel The Scarlet Pimpernel has been adapted for literally every medium possible, including a 1999 BBC series starring Richard E. Grant as the title character. And that doesn’t even touch on other novels about upheaval in France in the years following the French Revolution, from Alexander Chee’s The Queen of the Night and the grand-pere of them all, Victor Hugo’s Les Miserables.</p>'),
           ('On Walt Whitman, Unsung Newspaperman',
            'Philip Eil', '2018-09-15', 4.25, '<p>There are many professions that can rightly claim Walt Whitman as their own. He was, at different times in his life, a carpenter, a schoolteacher, a government clerk, a volunteer nurse, a printer, a typesetter, and the operator of a stationary store.</p><p>He was also, you might have heard, a poet.</p>'),
           ('The 12 Best Book Covers of June',
            null, '2019-06-27', 3.75, '<p>Another month of books, another month of book covers. In the summer, all the books start looking a little too similar for my taste: the shelves become awash in sunsets, large hats, and soft colors, all the covers bidding for inclusion in beach bags or the emotional equivalent. None of the below book covers fit into that category—each one is weird and bold and perfectly suited to the book at hand. That, not to mention their technicolor forests, outsize illustrations, and surreal senses of humor—is what makes these the the best book covers of the month.</p>'),
           ('The Grand Cultural Influence of Octavia Butler',
            'Emily Temple', '2019-06-21', 3.80, '<p>Tomorrow, June 22, would have been legendary SF novelist and short story writer Octavia Butler’s 72nd birthday. She died in 2006—much too young, at only 58—already a certified genius who had a profound impact on many readers and writers across the world. Not surprisingly, this includes many of the best writers of SF, fantasy, speculative fiction, and horror working today, and so to celebrate Butler’s birthday, I’ve collected a few of their thoughts on her influence.</p>'),
           ('What Gets Lost (and Found) in Translating Prose to Comics',
            'Tobias Carroll', '2019-01-08', 4.60, '<p>As goes language, so too goes form. Comics creators have long drawn on literary sources for inspiration or outright adaptation. We’ve moved far beyond the days of <em>Classics Illustrated</em>, wherein a condensed version of a novel was translated in a straightforward manner to words and pictures on a page. David Mazzucchelli’s adaptation of Paul Auster’s <em>City of Glass</em> is a notable work in its own right, and one that neatly blends the aesthetics of two distinctive artists.</p>'),
           ('Why We’ll Never Get Tired of Literary Retellings',
            'Meg Donohue', '2019-05-28', 4.95, '<p>I make an effort to read a wide variety of books, but the genre that I find myself drawn to time and again is retellings of classic novels. I’ve yet to hear about a new twist on a timeless tale that doesn’t sound compelling to me. In fact, it’s a niche of storytelling that I enjoy so much that I’ve written my own entry into the genre, a novel entitled <em>You, Me, and the Sea</em> that is inspired by Emily Bronte’s <em>Wuthering Heights</em>. As I worked on my novel, I spent a lot of time thinking about my favorite retellings, and what it is, exactly, that makes these stories so endearing to readers—and writers. What I’ve come to believe is that reimaginings present a unique delight to readers because they manage to combine the pleasure of surprising twists with the comfort of a familiar story.</p>');
    ```

5. Retrieve articles with the information about the author attached to each row (there should be 12 rows in the result and around 10 columns, including the article’s title, text, rating, and date as well as the author’s name and sex):

    ```postgresql
    SELECT * FROM public.articles LEFT JOIN public.authors ON authors.id=articles.id
    ```

6. To get the twelve rows, you must have used one of the constructions `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, or `FULL JOIN`. How many rows would the other three have returned? First try to think of the answers and then verify them by running the queries (it’s important you understand the results). Put the numbers below:

    ```
    INNER JOIN: 11
    LEFT JOIN: 12
    RIGHT JOIN: 13
    FULL JOIN: 14
    ```

7. Imagine you’re using pagination to display articles showing five articles per page. Retrieve the content for the first page: create a query that would return the latest five articles, ordered from the latest to the earliest.

    ```postgresql
    SELECT text FROM articles ORDER BY date DESC LIMIT 5
    ```

8. Retrieve the content for the second page: articles 6 through 10 (still assuming chronological order).

    ```postgresql
    SELECT text FROM articles ORDER BY date DESC LIMIT 5 OFFSET 5
    ```

9. Retrieve the content for the third page: articles 11 through 15 (never mind there are actually only 12 of them currently in the table).

    ```postgresql
    SELECT text FROM articles ORDER BY date DESC LIMIT 5 OFFSET 10
    ```

10. Count the number of five-article pages required to accommodate all articles:

    ```postgresql
    SELECT ceil(count(*)::double precision / 5) AS count_pages FROM articles
    ```

11. Calculate an average rating of the articles, rounded to the nearest integer:

    ```postgresql
    SELECT round(AVG(rating)) AS avg_rating FROM articles
    ```

12. Count males and females among the authors. There should be two rows (for males and females) and two columns: `sex` (`F` or `M`) and `cnt` (count).

    ```postgresql
    SELECT sex, COUNT(sex) AS cnt FROM authors GROUP BY sex
    ```

13. Find the date of the earliest (put in the column `earliest`) and latest (put in the column `latest`) article written by each author:

    ```postgresql
    SELECT author, MIN(date) AS earliest, MAX(date) AS latest FROM articles GROUP BY author
    ```

14. Calculate the total length of the text written by each author (count both `text` and `title`; you can keep the tags in `text` while counting):

    ```postgresql
    SELECT SUM(length_text) AS total_length, author FROM (SELECT author, LENGTH(title || text) as length_text  FROM articles) AS text GROUP BY author
    ```

15. Output all the authors in a random order. There should be only one column aliased `author` with the first and last name of the author concatenated (using a space, of course). The order of the rows should be different on each request:

    ```postgresql
    SELECT (first_name || ' ' || last_name) AS author FROM authors order by RANDOM()
    ```

16. "Anonymize" the authors: replace each author’s last name with the properly capitalized reverse of it. E.g., `Alofsin` should become `Nisfola`, `Esposito` should become `Otisopse`, etc.

    ```postgresql
    UPDATE authors SET last_name = INITCAP(REVERSE(last_name))
    ```

17. Delete all articles that don’t have an author:

    ```postgresql
    DELETE FROM articles WHERE author IS NULL
    ```

18. **(optional)** Delete all authors that haven’t written any articles:

    ```postgresql
    DELETE FROM authors WHERE id NOT IN (SELECT id FROM articles)
    ```

Don’t forget to create a pull request.
