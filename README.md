# Python-file-handling
Python file handling and exceptional handling

  def read_and_modify_file():
    try:
        # Ask user for input file name
        input_file = input("Enter the name of the file to read: ")
        
        # Open the file for reading
        with open(input_file, "r") as file:
            content = file.read()

        # Modify content (convert text to uppercase)
        modified_content = content.upper()

        # Define output file name
        output_file = "modified_" + input_file
        
        # Write modified content to new file
        with open(output_file, "w") as file:
            file.write(modified_content)

        print(f"File processed successfully! Modified file saved as: {output_file}")

    except FileNotFoundError:
        print("Error: The file does not exist. Please check the filename and try again.")
    
    except PermissionError:
        print("Error: You don’t have permission to read this file.")
    
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Run the function
read_and_modify_file()
