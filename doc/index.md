# Title
* Hayford Teye, 2.26.23*

## Introduction
Demonstrate the use of pickling and error function

## Topic
Pickling and Structure error Handling

```
# ....................................................... #
# Title: Pickling and Structure error handling
# Description: Demonstrate the use of pickling and error function
# Change log: Created script, 2/26/23
# dev: Hayford Teye, 2/26/23
# ........................................................ #

# -------------------- Data Section -------------------------#
import pickle  # import pickle modules

lstPickle = []
strGiftFile = "BirthdayGiftList.dmp"
strRecipient = input("Enter the gift recipient: ")

while True:
    try:
        intAge = int(input("Please enter the recipient's age: "))
    except ValueError:
        print("Please use whole numbers only for recipient's age")
        continue
    break

strGift = input("Please enter a gift idea for this person: ")
lstGifts = [strRecipient, intAge, strGift]

objFile = open(strGiftFile, 'ab')  # create files and open in it in append binary mode
pickle.dump(lstGifts, objFile)  # dump the list content in dump file
objFile.close()

strGo = input("\nPress any key to unpickle the data...\n")

objFile = open(strGiftFile, 'rb')  # Read content in binary file

while True:
    try:
        pklData = pickle.load(objFile)
        lstPickle.append(pklData)
    except EOFError:
        break

objFile.close()

print("These gherkin are unpickled!!")

print("-" * 30)

for pklData in lstPickle:
    print(pklData)
print("-" * 30)
input("Press enter key to exit the program...\n")
```
### Figure1
!.[Results of figure 1].(https://github.com/hteye/IntroToProg-Python-Mod07/blob/main/doc/output_7.png "Results of figure 1")
