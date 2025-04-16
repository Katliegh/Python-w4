# Python-w4

def modify_line(line):
    return line.strip().upper() + "\n"

def main():
    input_filename = input("Enter the name of the file to read: ")
    try:
        with open(input_filename, 'r', encoding='utf-8') as infile:
            lines = infile.readlines()
        modified_lines = [modify_line(line) for line in lines]
        output_filename = "modified_" + input_filename
        with open(output_filename, 'w', encoding='utf-8') as outfile:
            outfile.writelines(modified_lines)
        print(f"Modified file has been written to '{output_filename}'.")
    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' does not exist.")
    except IOError as e:
        print(f"Error reading or writing file: {e}")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

if __name__ == "__main__":
    main()
