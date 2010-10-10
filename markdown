#!/bin/bash
FILENAME="`echo -n $1 | sed s/.txt//`"
echo -e '<!DOCTYPE html>\n<html>\n<head>\n<meta charset="utf-8">\n<title>'$FILENAME'</title>\n<link rel="stylesheet" href="master.css">\n<meta name="viewport" content="width=device-width">\n</head>\n<body>' > "$FILENAME.html"
perl ~/Sites/Tools/Markdown.pl --html4tags "$FILENAME.txt" >> "$FILENAME.html"
echo -e '</body>\n</html>' >> "$FILENAME.html"