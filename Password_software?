import string
import random

# Things for for function
upper = list(string.ascii_uppercase)
lower = list(string.ascii_lowercase)
#------------------------------------
letters = upper + lower
punctuation= list(string.punctuation)
digits = list(string.digits)
#------------------------------------
chars = letters + punctuation + digits

# Password Generator
def generate_pw(length=12):
    random.shuffle(chars)
    final_chars = chars[:length]
    return "".join(final_chars)

# Start menu 
def start():

    print("\nOptions:")
    print("Option 1 - Generate a safe password")
    print("Option 2 - Check password strength")
    print("Option 3 - Quit program")
    
    # user input for choice
    user_input = input("which options would you like to choose?: ")
    return user_input

# Pasword strength measurer
def pw_strength(password):
    strength = 0
    extras = 0
        # This checks if the passwords has numbers.
    if any(chars in digits for chars in password):
        strength += 1
        # Read this pieace of code like this "for chars in password, if chars-
        # -is in string.punctuation, then it is True, triggering the addition.
        # This is checking if password has punctuation.
    if any(chars in string.punctuation for chars in password):
        strength += 1
        # Checks for lowercase letters.
    if any(chars in string.ascii_lowercase for chars in password):
        strength += 1 
        # Checks for Captialized/Uppercase letters.
    if any(chars in string.ascii_uppercase for chars in password):
        strength += 1 
        # Checks for the lenght of the password.
    if len(password) >= 12:
        strength += 1
    return strength




# Process when user chooses option 1 (password generator)
while True:
    print("\033[38;5;214m\nPASSWORD SOFTWARE\033[0m")
    print("Options:")
    print("Option 1 - Generate a safe password")
    print("Option 2 - Check password strength")
    print("Option 3 - Quit program")
    
    # user input for choice
    user_input = input("which options would you like to choose?: ")
    if not user_input.isdigit():
        print("\033[91mInput is not a number, try again! (make sure to type numbers not letters)\033[0m")
        continue

    if int(user_input) == 1:
        while True:
            print("\033[96m\nENTERED PASSWORD GENERATOR MODE\033[0m")
            password_lenght = input("Press 'q' to return to menu or... \nInput the number of characters for your password(minimum 12): ")
            if password_lenght.isdigit() and int(password_lenght) < 12:
                print("\npassword too short!")
                continue
            elif password_lenght.isdigit() and int(password_lenght) > 12 or  password_lenght.isdigit() and int(password_lenght) == 12:
                print("\nGenerating password........")
                # new generated password<>
                new_pw = generate_pw(int(password_lenght))
                print(f"This is your new generated password: \033[38;5;135m{new_pw}\033[0m")
                # For invalid user input
            elif password_lenght == float:
                print("please enter a whole number 'not decimals!'")
                # Exit the program
            elif password_lenght.lower() == 'q':
                print("\033[38;5;160mreturning to menu...\033[0m")
                break
            else:
                print("\033[91mError, try again!\033[0m")
                continue
        continue
    elif int(user_input) == 2:
        while True:
            print("\033[38;5;220m\nENTERED PASSWORD CHECKER MODE\033[0m")
            password_check = input("Press 'q' to return to menu or... \nInput your password to check if it is strong or not: ")
            if password_check.lower() == "q":
                print("\033[38;5;160mRetunring to menu\033[0m")
                break
            elif pw_strength(password_check) == 0:
                print("\033[38;5;160mYour password is EXTREMELY WEAK,\033[0m")
                continue
            elif pw_strength(password_check) == 1:
                print("\033[38;5;196mYour password is VERY WEAK\033[0m")
                continue
            elif pw_strength(password_check) == 2:
                print("\033[38;5;208mYour password is WEAK \033[0m")
                continue
            elif pw_strength(password_check) == 3:
                print("\033[38;5;34mYour password is SOMEWHAT STRONG\033[0m")
                continue
            elif pw_strength(password_check) == 4:
                print("\033[38;5;46mYour password is STRONG\033[0m")
                continue
            elif pw_strength(password_check) == 5:
                print("\033[38;5;120mYour password is IMPENETRABLE\033[0m")
                continue
            else:
                print("\033[91mError, try again ig?\033[0m")
                continue
        continue
    elif int(user_input) == 3:
        print("\033[95m\nClosing program...\033[0m")
        break
    else:
        print("\033[95m\nError on input, please input the correct value!\033[0m")
        continue



