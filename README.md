# WebDevWorkshop with Docker and Django

Welcome to the "Web Development Essentials" workshop! This repository is a companion to the 30-minute introduction to web development workshop, led by Joe Crowley. It's designed to guide you through the basics of web development using HTML, CSS, and JavaScript, and then transition you into creating a "Hello World" project with Django inside a Docker container.

## Workshop Structure

This workshop is divided into several parts, each focusing on a different aspect of web development:

1. **Basic HTML/CSS/JavaScript**: We'll start by creating a simple web page with some styling and interactive elements using JavaScript.
2. **Introduction to Docker**: Here, we'll introduce Docker, a powerful tool that helps to create, deploy, and run applications by using containers.
3. **Building with Django**: We'll move our simple web page into a Django application and understand the basics of web applications in Python.
4. **(Bonus) User Authentication**: As a bonus, we will discuss how to add a user authentication system to our Django project.

## Prerequisites

Before you attend the workshop, please ensure you have the following installed:

- [Docker](https://docs.docker.com/get-docker/)
- [Git](https://git-scm.com/downloads)
- A text editor of your choice (e.g., [Vim](https://www.vim.org), [Emacs](https://www.gnu.org/software/emacs/), [VSCode](https://code.visualstudio.com/download))

## How to Use This Repository

Each part of the workshop has its own directory and `README.md` with detailed explanations and step-by-step guides.

- `Part1_Basic_HTML_CSS_JS`: Contains a simple HTML file with CSS and JavaScript.
- `Part2_Docker`: Includes the Docker configuration files to set up your Django environment.
- `Part3_Django`: The main Django project with templates and view files.

Follow along with the workshop by reading through each `README.md` and coding along with the provided examples.

## Getting Started

1. Clone this repository to your local machine using:
   ```
   git clone https://github.com/joseph-crowley/web-dev-workshop.git
   ```
2. Navigate to each part's directory to find the resources and instructions:
   ```
   cd Part1_Basic_HTML_CSS_JS
   ```
3. Follow the instructions in the `README.md` file within each directory to proceed with the exercises.

## Support

If you encounter any problems or have questions, please open an issue in this repository.

## Contributing

Feel free to fork this repository and submit pull requests to contribute to this project. Whether it's improving the documentation or adding new features, your contributions are welcome!

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgements

Thank you to all participants for joining the workshop, and to the open-source community for providing the tools and resources that make projects like this possible.

# Note for Windows Users

When using this workshop repository on a Windows machine, please consider the following adjustments to ensure compatibility:

- **Docker Installation**: Windows requires WSL2 (Windows Subsystem for Linux version 2) for Docker Desktop. Make sure WSL2 is installed and set up before installing Docker. Follow the [Windows-specific Docker installation guide](https://docs.docker.com/docker-for-windows/install/).

- **File Paths**: Use Windows-style backslashes (`\`) for navigating directories in command-line interfaces like PowerShell or Git Bash.

- **Git for Windows**: Upon installing Git, it's recommended to choose Git Bash as your command-line interface, which allows for Unix-style commands.

- **Command Line Tools**: Use PowerShell or Git Bash for command-line operations as they are more compatible with Unix-style commands.

- **Line Endings**: Git on Windows may change line endings to CRLF (Carriage Return and Line Feed). To prevent this, you can disable automatic conversion using the following command in Git Bash or PowerShell:
  ```
  git config --global core.autocrlf input
  ```
  This ensures that your Docker containers, which expect LF (Line Feed) line endings, function correctly.

- **Text Editors**: Editors like Notepad++, Visual Studio Code, or the integrated editor in WSL are recommended for a better experience when editing code files on Windows.

- **File Permissions**: If you encounter file permission issues, especially when using volumes with Docker, you may need to adjust the settings within Docker for Windows or modify the file permissions directly in Windows.

- **Environment Variables**: Setting environment variables on Windows can differ from Unix systems. In PowerShell, use `$env:VAR_NAME="value"` to set a variable. In Command Prompt, use `set VAR_NAME=value`.

- **Networking**: Docker networking functions similarly across platforms, but ensure that any firewall or antivirus programs do not block the required ports.

- **Running Scripts**: If there are any .sh (bash) scripts, they should be run in Git Bash or WSL to ensure compatibility. Alternatively, they can be translated to PowerShell scripts if needed.

- **WSL Integration**: For an experience closer to Unix-like environments, consider using WSL. It allows you to run a Linux distribution alongside your Windows environment.

By keeping these points in mind, Windows users should have a seamless experience with the workshop materials. Should you encounter any issues, don't hesitate to open an issue in this repository for support.