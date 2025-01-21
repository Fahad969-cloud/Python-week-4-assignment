Create a program that reads a file and writes a modified version to a new file.

def modify_file_content(content):
    """
    Function to modify file content.
    For this example, it converts text to uppercase.
    You can customize this logic as needed.
    """
    return content.upper()

def main():
    try:
        
        input_file = input("Enter the name of the file to read: ")

        
        with open(input_file, "r") as file:
            content = file.read()

        modified_content = modify_file_content(content)

      
        output_file = input("Enter the name of the new file to write: ")

        
        with open(output_file, "w") as file:
            file.write(modified_content)

        print(f"Modified content has been written to {output_file}.")

    except FileNotFoundError:
        print("Error: The file does not exist.")
    except IOError:
        print("Error: Could not read or write to the file.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

if __name__ == "__main__":
    main()

    Ask the user for a filename and handle errors if it doesn’t exist or can’t be read.
    def read_file(filename):
    try:
      
        with open(filename, 'r') as file:
            content = file.read()
            print("File content:")
            print(content)
    
    except FileNotFoundError:
        print(f"Error: The file '{filename}' does not exist.")
    
    except IOError:
        print(f"Error: Could not read the file '{filename}'. It may be corrupted or you don't have permission to read it.")


filename = input("Enter the filename: ")

read_file(filename)


