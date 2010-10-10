#!/bin/bash
FILENAME="`echo -n $1 | sed s/.txt//`"
echo -e '<!DOCTYPE html>\n<html>\n<head>\n<title>'$FILENAME'</title>\n<meta charset="utf-8">\n</head>\n<body>' > "$FILENAME.html"
perl ~/Sites/Tools/Markdown.pl --html4tags "$FILENAME.txt" >> "$FILENAME.html"
echo -e '</body>\n</html>' >> "$FILENAME.html"