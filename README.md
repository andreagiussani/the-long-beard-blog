# The Long Beard Blog

## Access to the Blog
Visit the following [link](https://andreagiussani.github.io/the-long-beard-blog/)

## How to Locally Set up GitHub Pages 
To install all the necessary tools and dependencies to work with GitHub Pages locally (including jekyll and the required gems) using Homebrew on macOS, follow this step-by-step guide.

### Step 1: Install Homebrew (If Not Already Installed)
Homebrew is a package manager for macOS that allows you to easily install various software, including Ruby and other dependencies.
To install Homebrew, run the following command in your terminal:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

###  Step 2: Install Ruby
GitHub Pages and Jekyll require Ruby to run, and it's best to install it using Homebrew.
To install the latest version of Ruby, run the following command:
```
brew install ruby
```

###  Step 3: Update Your PATH to Use Homebrew's Ruby
After installing Ruby through Homebrew, you need to make sure your system uses Homebrew's version of Ruby. This is done by updating your PATH.
Open your terminal and add the following line to your .bash_profile (for bash) or .zshrc (for zsh, the default shell on newer macOS versions):
```bash
export PATH="/opt/homebrew/opt/ruby/bin:$PATH"
```

Then, run the following command to reload the shell configuration:
source ~/.bash_profile  # or source ~/.zshrc if you're using zsh

###  Step 4: Install Bundler and Jekyll
Next, you need to install the Bundler and Jekyll gems. Bundler is used to manage Ruby gem dependencies, and Jekyll is the static site generator you'll use to build and serve your GitHub Pages site locally.
To install Bundler, run:
```bash
gem install bundler
gem install jekyll
```

###  Step 5: Install Other Dependencies for GitHub Pages
GitHub Pages often requires other dependencies that are packaged together in a specific gem called github-pages. To install it, follow these steps:
Navigate to your project directory (where your Gemfile is located). For example: `cd /path/to/your/github/pages/project`

Install all the gems specified in the Gemfile using Bundler:
```bash
bundle install
```

This command will install all dependencies listed in your Gemfile, including Jekyll, GitHub Pages, and other necessary gems.
###  Step 6: Running Jekyll Locally
After everything is installed, you can serve your GitHub Pages site locally to preview it.
Run the following command from your project directory:
```bash
bundle exec jekyll serve
```

This will build and serve your site at http://localhost:4000 by default. Open that URL in your browser to see your site.

### Troubleshooting
If you run into any issues during installation, here are a few common solutions

#### 1. Install Xcode Command Line Tools:
```bash
xcode-select --install
```


#### 2. Install Autoconf and other build tools via Homebrew:
```bash
brew install autoconf
```

####  3. Bundler or Jekyll not found
If you get a "command not found" error, it may be because the Ruby version installed by Homebrew isn't in your PATH. Make sure you've updated your PATH to include Homebrew's Ruby location as mentioned earlier.


####  4. Permission issues
If you run into permissions errors while installing gems, try installing gems with sudo (though this is rare with Homebrew's Ruby installation).


### Step 7: Updating Dependencies
To update your dependencies (such as Jekyll or any gems listed in your Gemfile), run:
```bash
bundle update
```


To update your Ruby version with Homebrew, you can simply run:
```bash
brew upgrade ruby
```
Then follow the steps to update your PATH if necessary.
