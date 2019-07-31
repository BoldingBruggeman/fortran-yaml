src_dir: ./
output_dir: ~/BB/hugo/static/portfolio/yaml/doc
project_github: https://github.com/BoldingBruggeman/fortran-yaml
project_website: https://github.com/BoldingBruggeman/fortran-yaml
summary: A lightweight YAML parser written in object-oriented Fortran
author: Jorn Bruggeman
author_description:
github: https://github.com/jornbr
email: jorn@bolding-bruggeman.com
fpp_extensions: fpp
predocmark: >
media_dir: ./media
docmark_alt: #
predocmark_alt: <
display: public
         protected
         private
source: false
graph: true
search: true
macro: TEST
       LOGIC=.true.
extra_mods: json_module: http://jacobwilliams.github.io/json-fortran/
            futility: http://cmacmackin.github.io
license: by-nc
extra_filetypes: sh #

Hi, my name is ${USER}.

This is a project which I wrote. This file will provide the documents. I'm
writing the body of the text here. It contains an overall description of the
project. It might explain how to go about installing/compiling it. It might
provide a change-log for the code. [[linalg]] Maybe it will talk about the
history and/or motivation for this software.

@Note
You can include any notes (or bugs, warnings, or todos) like so.

@Bug
You can have multi-paragraph versions of these too! That means you can
include

- ordered lists
- unordered lists
- images
- etc.

Isn't that cool?
@endbug

@Bug Hey I'm doing it again...

This ones ends mid...@endbug ...paragraph.

You can have as many paragraphs as you like here and can use headlines, links,
images, etc. Basically, you can use anything in Markdown and Markdown-Extra.
Furthermore, you can insert LaTeX into your documentation. So, for example,
you can provide inline math using like \( y = x^2 \) or math on its own line
like \[ x = \sqrt{y} \] or $$ e = mc^2. $$ You can even use LaTeX environments!
So you can get numbered equations like this:
\begin{equation}
  PV = nRT
\end{equation}
So let your imagination run wild. As you can tell, I'm more or less just
filling in space now. This will be the last sentence.

