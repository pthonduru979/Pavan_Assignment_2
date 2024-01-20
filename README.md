# Pavan_Assignment_2
def fullname(first_name, last_name):
    full_name = first_name + " " + last_name
    return full_name

def string_alternative(input_string):
    result = input_string[::2]
    return result

def main():
    first_name = input("Enter your first name: ")
    last_name = input("Enter your last name: ")

    full_name = fullname(first_name, last_name)
    print("Full Name:", full_name)

    alternated_string = string_alternative(full_name)
    print("Every Other Character in Full Name:", alternated_string)

if __name__ == "__main__":
    main()






def count_words(line):
    words = line.split()
    word_count = {}

    for word in words:
        if word in word_count:
            word_count[word] += 1
        else:
            word_count[word] = 1

    return word_count

def main():
    try:
        with open('inputdata.txt', 'r') as input_file:
            lines = input_file.readlines()

        output_lines = ["Output:"]
        for line in lines:
            line = line.strip()
            output_lines.append(line)

        output_lines.append("Word_Count:")
        word_count = {}
        for line in lines:
            count = count_words(line)
            for word, freq in count.items():
                if word in word_count:
                    word_count[word] += freq
                else:
                    word_count[word] = freq

        for word, freq in word_count.items():
            output_lines.append(f"{word}: {freq}")

        with open('output.txt', 'w') as output_file:
            output_file.write('\n'.join(output_lines))

        print("Output written to output.txt")

    except FileNotFoundError:
        print("input_data.txt not found")

if __name__ == "__main__":
    main()


def convert_heights_to_cm():
    num_customers = int(input("Enter the number of customers: "))
    heights_inches = []

    for i in range(num_customers):
        height_inches = float(input(f"Enter the height (in inches) for customer {i + 1}: "))
        heights_inches.append(height_inches)

    heights_cm = []

    for height_inches in heights_inches:
        height_cm = height_inches * 2.54
        heights_cm.append(round(height_cm, 2))

    return heights_cm

if __name__ == "__main__":
    converted_heights = convert_heights_to_cm()
    print("Converted heights (in cm):", converted_heights)



def convert_heights_to_cm():
    num_customers = int(input("Enter the number of customers: "))
    heights_inches = [float(input(f"Enter the height (in inches) for customer {i + 1}: ")) for i in range(num_customers)]
    heights_cm = [round(height * 2.54, 2) for height in heights_inches]
    return heights_cm

if __name__ == "__main__":
    converted_heights = convert_heights_to_cm()
    print("Converted heights (in cm):", converted_heights)






