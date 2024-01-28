from __future__ import print_function
import argparse
import random
import string
import math
generate = float(input("How Many MAC & RID You Want Generate ? ")) ## How Many Guest U Want Generate
## HOW TO ADD SEPARATORS :
## py filename.py -s (separator)
## Colon = :      <====== DEFAULT
## Dash = -
## none = no space
## space = with space
##================ DO NOT CHANGE ================
SEPARATORS = {
    'colon': ':',
    'dash': '-',
    'none': '',
    'space': ' ',
}

def parse_args():
    parser = argparse.ArgumentParser(description='Generate random MAC address')
    parser.add_argument('-s', '--separator',
                        choices=sorted(SEPARATORS.keys()), default='colon',
                        help='What separator to use between the bytes in the output.')
    return parser.parse_args()

def main():
##====================== RID ======================
    args = parse_args()

    rid = [ random.randint(0, 255) for x in range(16) ]
    rid[0] = (rid[0] & 0xfc) | 0x02
    rid = ''.join(['{0:02x}'.format(x) for x in rid])

##====================== mac ======================
    args = parse_args()
    separator = SEPARATORS[args.separator]

    mac = [ random.randint(0, 255) for x in range(0, 6) ]
    mac[0] = (mac[0] & 0xfc) | 0x02
    mac = separator.join([ '{0:02x}'.format(x) for x in mac ])
    result = (mac.upper()+'|'+rid.upper())
    f = open("result.txt", "a")
    f.writelines(result+"\n")
    f.close()
    print(result)

count = 0
while count < generate and __name__ == '__main__':
    main()
    count += 1
while count == generate:
    print("Succesfully Create", generate, "MAC & RID. Check result.txt")
    break
