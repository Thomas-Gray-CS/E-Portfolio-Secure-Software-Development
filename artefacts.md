Secure Software Development - Artefacts 

On this page are a number of artefacts that I have gather from my studies of Secure Software Development as part of my MSc Computer Science course. These show my development relating to secure coding, data security and legal compliance.


### Unit 2: UML Modelling to Support Secure System Planning

Below is a discussion on ISO/IEC 27000 and how people management techniques can ensure compliance of this.

[ISO/IEC 27000 Standards](/pdf/individuals_security.pdf)


### Unit 4: Exploring Programming Language Concepts

Below is an article regarding ReDOS and regex.

[ReDOS and Regex](/pdf/redos_regex.pdf)

Below is a program that uses regex to check postcodes and assert whether they are real or not:

```
       import re #re is a standard library for regex

# Define the regex pattern for UK postcodes 
# regex taken from UK Government Archive on postcode types
postcode_pattern = re.compile(r"^(GIR 0AA|[A-Z]{1,2}[0-9R][0-9A-Z]? [0-9][A-Z]{2})$")

# data for testing inputted, with the "DN" postcode changed to give error

postcodes = [
    "M1 1AA",
    "M60 1NW",
    "CR2 6XH",
    "DNI99 1PT",
    "W1A 1HQ",
    "EC1A 1BB"
]

# Function to validate postcodes and output Boolean for answer

def validate_postcode(postcode):
    if len(postcode) > 8:  # this ensures maximum potential input isn't exceeded, avoiding evil regex
        return False
    if postcode_pattern.match(postcode):
        return True
    else:
        return False

# Testing function to print all postcode checks

for postcode in postcodes:
    print(f"{postcode}: {validate_postcode(postcode)}")

```

### Unit 5: An Introduction to Testing

Below is a discussion regarding the relevance of Cyclomatic Complexity in modern day programming.

[Exploring the Cyclomatic Complexity’s Relevance Today](/pdf/cyclomatic_complexity.pdf)


### Unit 6: Using Linters to Support Python Testing

Below is a link to the group assignment completed during this module.

[Team Assignment](/team_assignment.md)


### Unit 8: Cryptography and Its Use in Operating Systems

Below is a discussion on an encryption algorithm, and whether it is effective.

[Cryptography Programming Exercise](/pdf/encryption_algorithm.pdf)

Below is my initial post on a discussion regarding TrueCrypt.

[Collaborative Discussion Initial Post](/pdf/truecrypt_initial.pdf)


### Unit 9: Developing an API for a Distributed Environment

Below is a response I provided to another student in reference to the work in Unit 8.

[Peer Response](/pdf/response_ssd.pdf)


### Unit 10: From Distributed Computing to Microarchitectures

Below is my summary post from the discussions in Unit 8 and Unit 9.

[Summary Post](/pdf/summary_ssd.pdf)


### Unit 11: Future trends in Secure Software Development

Below is a link to the group assignment completed during this module.

[Individual Assignment](/individual_assignment.md)






