---
layout: post
title:  "Jekyll on Ubuntu: Setup and default site build"
date:   2021-02-27 21:28:54 +0530
categories: jekyll setup
---
This post will take you through the complete step-by-step procedure of installing and making Jekyll static site builder functional on your machine.

## 1. Installation process:

Ruby Development Environment:

Jekyll require Ruby version 2.5.0 or above, including all development headers. Check ruby version:

- Open your terminal ( CTRL + ALT + T).
- Check for Ruby environment using the command ruby -v in your terminal. If the command doesn’t output the required version of Ruby 2.5.0 or above, then do the following:

  - Run the following command in your terminal:
    ```bash
    sudo apt-get install ruby-full
    ```
  - Now run the following commands in your terminal:
    ```
    ruby -v
    gem -v
    ```

  They both should return appropriate versions available on the system.

Make sure that “GCC” and “Make” are installed on your system ( check by running `gcc -v`, `g++ -v` and `make -v` in your terminal). If not, head over to their official website for installation instructions: [GCC](https://gcc.gnu.org/install/) and [Make](https://www.gnu.org/software/make/).

Install all the required dependencies before we install Jekyll by running the following command in your terminal:

```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
```

It’s a good practice to create a gem installation directory for your user account. Run the following commands in your terminal. These will add environment variables to your ```~/.bashrc```.

```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

Finally install Jekyll:
```bash
gem install jekyll bundler
```

That’s all, you are good to go to start using Jekyll.

## 2. Check Jekyll for a test site.
- Open your terminal and change the directory to a suitable path where you want to initialize and store your Jekyll project. (We’ll use “testSite” as our root directory for project).

- Run the following command to initialize a new Jekyll site:

  ```bash
  jekyll new testSite
  ```

- Change into the new directory:

  ```bash
  cd testSite
  ```

- Now run the following command to build and host the site on local server:

  ```bash
  bundle exec jekyll serve
  ```

- Browse to localhost:4000 in your browser. There you go, you should see the default Welcome to Jekyll page. Note: You can stop the server by pressing CTRL + C in your terminal window which is showing server running. 


So now you have:

- Installed the Jekyll and related development environment on your system.
- Built and hosted the default page on your local server.