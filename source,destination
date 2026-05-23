source_filename = "source.txt"
destination_filename = "reversed.txt"

source_data = input("Enter the text you want to save and reverse: ")
file_write = open(source_filename, "w")
file_write.write(source_data)
file_write.close()

file_read = open(source_filename, "r")
content = file_read.read()
file_read.close()

# Reverse the content character by character
# [::-1] creates a reversed copy of the string
reversed_content = content[::-1]

file_dest = open(destination_filename, "w")
file_dest.write(reversed_content)
file_dest.close()

print(f"\nOriginal data saved in '{source_filename}': {content}")
print(f"Reversed data saved in '{destination_filename}': {reversed_content}")
