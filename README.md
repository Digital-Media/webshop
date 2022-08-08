# Exercises with the webshop repo

This repository provides Exercises for web development classes at the [Upper Austria University of Applied Sciences (FH Oberösterreich), Hagenberg Campus](https://www.fh-ooe.at/en/hagenberg-campus/).

## Installation

See [INSTALL.md](https://github.com/Digital-Media/webshop/blob/main/INSTALL.md)

# hyp2ue3_t1

This Exercise makes you familiar with the concept of __*PHP templates and Routing*__.
We use __*Twig*__ as one of many php template engines.
This ist done as __*Code Along*__ session to get familiar with the file structure and dependencies in a PHP project using __*composer*__ to install Twig.
We create an __*HTML input form*__ to write data to a database.
See the documentation for the already installed components we use.
- [Twig](https://twig.symfony.com/)
- [Composer](https://getcomposer.org/)

# hyp2ue5_t2

This Exercise makes you familiar with the concepts of a __*database driver*__. We use __*PDO*__ for serveral reasons.
It supports many databases and is the basis for the database framework doctrine used in the PHP framework symfony for example.
This ist done as __*Code Along*__ session and we will add data to the table `onlineshop.country`.
This Exercise is related to hyp2ue3_t1.

# hyp2ue4_t1

This Exercise uses the knowledge form hyp2ue3_t1 to build a template for a Registration form.

# hyp2ue6_t2

This Exercise uses the knowledge from hyp2ue5_t2 to store data of a Registration form to `onlineshop.user`.
It is related to hyp2ue4_t1.

# hyp2ue5_t1

This Exercise uses the knowledge form hyp2ue3_t1 to build a template for a Login form.

# hyp2ue7_t2

This Exercise uses the knowledge from hyp2ue5_t2 to store data of a Login form to authenticate against `onlineshop.user`.
It is related to hyp2ue5_t1.

# hyp2ue8_t2

This Exercise uses the knowledge form hyp2ue3_t1 to build a template for a form to add products to `onlineshop.product`.
This Exercise uses the knowledge from hyp2ue5_t2 to store data of the Product form in `onlineshop.product`.
