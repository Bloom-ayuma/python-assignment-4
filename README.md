# python-assignment-4
File Read & Write Challenge 🖋️: Create a program that reads a file and writes a modified version to a new file.
Error Handling Lab 🧪: Ask the user for a filename and handle errors if it doesn’t exist or can’t be read.
Outcomes 🎉

By the end of this module, you’ll be skilled in managing files efficiently in Python, ensuring error-free code that gracefully handles unexpected issues. Mastering files and exception handling will allow you to build strong, robust applications!
1. Code for Reading, Modifying, and Writing to a File
def read_and_write_file(source_file, destination_file):
    try:
        # Step 1: Open the source file to read
        with open(source_file, "r") as file:
            content = file.read()  # Read the entire content

        # Step 2: Modify the content (convert to uppercase)
        modified_content = content.upper()

        # Step 3: Write the modified content to a new destination file
        with open(destination_file, "w") as new_file:
            new_file.write(modified_content)

        print(f"Modified content has been successfully written to {destination_file}")
    
    # Error Handling
    except FileNotFoundError:
        print(f"Error: The file {source_file} does not exist.")
    except PermissionError:
        print(f"Error: Permission denied to read or write the file.")
    except IOError as e:
        print(f"Error: An I/O error occurred: {e}")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")


# Main function to run the file reading and writing operation
def main():
    # Ask the user for the filenames
    source_file = input("Enter the source filename to read from: ")
    destination_file = input("Enter the destination filename to save modified content: ")

    # Call the function that handles the file reading, modification, and writing
    read_and_write_file(source_file, destination_file)

if __name__ == "__main__":
    main()
2. Ask User for Filename and Handle Errors
python
def handle_file_error():
    filename = input("Please enter the filename: ")

    try:
        # Try to open and read the file
        with open(filename, "r") as file:
            content = file.read()
            print(f"Content of {filename}:\n{content}")
    
    # Handle specific errors
    except FileNotFoundError:
        print(f"Error: The file '{filename}' was not found.")
    
    except PermissionError:
        print(f"Error: You do not have permission to read '{filename}'.")
    
    except IOError as e:
        print(f"Error: An I/O error occurred while trying to read '{filename}'. {e}")
    
    # General exception handling
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Run the error handling function
handle_file_error()
