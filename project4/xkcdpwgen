{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "#!/usr/bin/env python3\n",
    "\n",
    "from random import randint\n",
    "import sys, getopt\n",
    "\n",
    "words = 4\n",
    "caps = 0\n",
    "numbers = 0\n",
    "symbols = 0\n",
    "special = [\"!\", \"@\", \"#\", \"$\", \"%\", \"^\", \"&\", \"*\", \"(\", \")\", \"-\", \"_\", \"=\", \"+\", \"<\", \">\", \"?\", \"~\"]\n",
    "\n",
    "try:\n",
    "    opts, args = getopt.getopt(sys.argv[1:], \"hc:w:n:s:\", [\"help\", \"caps=\", \"words=\", \"numbers=\",\n",
    "                                                           \"symbols=\"])\n",
    "except getopt.GetoptError:\n",
    "    print(\"usage: xkcdpwgen [-h] [-w WORDS] [-c CAPS] [-n NUMBERS] [-s SYMBOLS]\")\n",
    "    sys.exit(2)\n",
    "for opt, arg in opts:\n",
    "    if opt in ('-h', \"--help\"):\n",
    "        print(\"usage: xkcdpwgen [-h] [-w WORDS] [-c CAPS] [-n NUMBERS] [-s SYMBOLS]\\n\\n\" +\n",
    "              \"Generate a secure, memorable password using the XKCD method\\n\\n\" +\n",
    "              \"optional arguments:\\n\" +\n",
    "              \"    -h, --help            show this help message and exit\\n\" +\n",
    "              \"    -w WORDS, --words WORDS\\n\" +\n",
    "              \"                          include WORDS words in the password (default=4)\\n\" +\n",
    "              \"    -c CAPS, --caps CAPS  capitalize the first letter of CAPS random words\\n\" +\n",
    "              \"                          (default=0)\\n\" +\n",
    "              \"    -n NUMBERS, --numbers NUMBERS\\n\" +\n",
    "              \"                          insert NUMBERS random numbers in the password\\n\" +\n",
    "              \"                          (default=0)\\n\" +\n",
    "              \"    -s SYMBOLS, --symbols SYMBOLS\\n\" +\n",
    "              \"                          insert SYMBOLS random symbols in the password\\n\" +\n",
    "              \"                          (default=0)\")\n",
    "        sys.exit()\n",
    "    elif opt in (\"-w\", \"--words\"):\n",
    "        words = int(arg)\n",
    "    elif opt in [\"-c\", \"--caps\"]:\n",
    "        caps = int(arg)\n",
    "    elif opt in [\"-n\", \"--numbers\"]:\n",
    "        numbers = int(arg)\n",
    "    elif opt in [\"-s\", \"--symbols\"]:\n",
    "        symbols = int(arg)\n",
    "\n",
    "with open('words.txt') as f:\n",
    "    lines = f.read().splitlines()\n",
    "\n",
    "pwd = ''\n",
    "for i in range(words):\n",
    "    x = randint(0, len(lines) - 1)\n",
    "    temp = lines[x]\n",
    "    if caps >= (words - i):\n",
    "        temp = temp[0].upper() + temp[1:]\n",
    "    elif caps > 0:\n",
    "        if randint(0, words) < caps:\n",
    "            temp = temp[0].upper() + temp[1:]\n",
    "            caps -= 1\n",
    "    pwd += temp\n",
    "\n",
    "for j in range(numbers):\n",
    "    x = randint(0, len(pwd) - 1)\n",
    "    pwd = pwd[0:x] + str(randint(0, 9)) + pwd[x:]\n",
    "\n",
    "for x in range(symbols):\n",
    "    x = randint(0, len(pwd) - 1)\n",
    "    pwd = pwd[0:x] + special[randint(0, len(special) - 1)] + pwd[x:]\n",
    "\n",
    "print(pwd)"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3.9.6 64-bit",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "name": "python",
   "version": "3.9.6"
  },
  "orig_nbformat": 4,
  "vscode": {
   "interpreter": {
    "hash": "31f2aee4e71d21fbe5cf8b01ff0e069b9275f58929596ceb00d14d90e3e16cd6"
   }
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2
}
