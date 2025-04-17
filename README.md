# Google Colab Keyboard Shortcuts Guide

## Default Jupyter Commands (Preserved)

| Shortcut | Action | Description |
|----------|--------|-------------|
| `Shift+Enter` | Run cell and move to next | Execute current cell and move to the next one |
| `Ctrl+Enter` | Run cell without moving | Execute cell without changing position |
| `Alt+Enter` | Run cell and insert below | Execute cell and create a new one below |
| `Up/Down Arrow` | Navigate between cells | Move cursor between different cells |
| `a` | Create cell above | Insert a new cell above the current one |
| `b` | Create cell below | Insert a new cell below the current one |
| `?function-name` | Show definition and docstring | Display quick help about functions |
| `??function-name` | Show source code | Display the implementation of functions |
| `Shift+Tab` (press once) | View function parameters | Show function signature |
| `Shift+Tab` (press three times) | Get additional information | Show detailed function documentation | Opens up a new window

## Remapped Shortcuts (Using Ctrl+M prefix)

| Action | Shortcut | Original Shortcut | Description |
|--------|----------|-------------------|-------------|
| Delete Cell | `Ctrl+M D` | `d d` (press twice) | Remove the current cell |
| Merge Selected Cells | `Ctrl+M M` | `Shift+M` | Combine multiple selected cells |
| Convert to Code Cell | `Ctrl+M Y` | `y` | Change cell type to code |
| Convert to Markdown Cell | `Ctrl+M X` | `m` | Change cell type to markdown |

## Runtime Management

| Action | Shortcut | Description |
|--------|----------|-------------|
| Connect to Runtime | `Ctrl+M 1` | Connect to a computational backend |
| Disconnect Runtime | `Ctrl+M 0` | Disconnect from the current runtime |
| Restart Runtime | `Ctrl+M R` | Reset the current runtime (same as Reset Kernel) |
| Restart and Run All | `Ctrl+M A` | Restart runtime and execute all cells |

## Useful Magic Commands

Colab supports various magic commands that enhance your notebook experience:

```python
# Display visualizations directly in the notebook
%matplotlib inline

# Measure execution time of code
%timeit function_or_operation()
```

### When to use `%matplotlib inline`
- Include at the beginning of notebooks with visualizations
- Ensures plots appear directly below the cell that generates them
- Only needs to be run once per notebook session

### When to use `%timeit`
- For performance testing and optimization
- Automatically runs your code multiple times to get reliable timing
- Useful for comparing different implementations of the same functionality

Example:
```python
# Compare performance of different approaches
%timeit [i for i in range(1000)]
%timeit list(range(1000))
```

## Why This Configuration Works

1. **Preserves Familiar Commands**: Keeps the most common Jupyter shortcuts intact
2. **Simplifies Complex Operations**: Uses Ctrl+M prefix for less frequent operations
3. **Consistent Pattern**: Related functions use similar patterns, reducing cognitive load
4. **Runtime Focus**: Streamlined runtime management with intuitive shortcuts

## TODO: JavaScript Implementation

A custom JavaScript implementation can automate these remappings. This will be added in a future update and would allow:

1. Automatic shortcut configuration
2. Persistent settings across sessions
3. Additional customizations not available in the standard interface




## Installation Instructions

### Temporary Installation (Session Only)

1. Open your Google Colab notebook
2. Press `F12` to open developer console
3. Go to the "Console" tab
4. Copy and paste the JavaScript code from the `colab_remaps.js` file
5. Press Enter to execute the script
6. Your new keyboard shortcuts are now active for the current session

### Permanent Installation Options

#### Option 1: Create a Bookmarklet
1. Create a new bookmark in your browser
2. Set the name to "Colab Remaps" or similar
3. Paste the following in the URL field (make sure to include `javascript:` at the beginning):
   ```
   javascript:(function(){/* Paste the entire code from colab_remaps.js here */})();
   ```
4. Click the bookmark whenever you open a Colab notebook

#### Option 2: Use a Browser Extension
1. Install the Tampermonkey extension ([Chrome](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo), [Firefox](https://addons.mozilla.org/en-US/firefox/addon/tampermonkey/))
2. Create a new script that runs on `https://colab.research.google.com/*`
3. Paste the code from `colab_remaps.js` file into the script
4. Save the script and it will run automatically on Colab pages

## Contribute

Feel free to customize these shortcuts to better suit your workflow! The JavaScript file will be well-commented and easy to modify.

## License

This project is licensed under the APACHE License 2.0 - see the LICENSE file for details.
