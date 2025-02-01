# PHP Toast Notification Snippet

This repository provides a simple PHP snippet for displaying toast notifications. It uses PHP, JavaScript, and Tailwind CSS (optional) to create success and error notifications that fade out automatically after a set duration.

## Features

- **Success Toast:** Displays a green toast notification that fades out after 3 seconds.
- **Error Toast:** Displays a red toast notification that fades out after 8 seconds.
- **Easy Integration:** Just set the `$success` or `$err` variable in your PHP code, and the corresponding toast notification will appear.
- **Customizable:** Adjust timeout durations, styles, or positioning to fit your needs.

## Requirements

- **PHP:** Version 5.6 or later.
- **Tailwind CSS (Optional):** The snippet uses Tailwind CSS classes for styling. You can replace these with your own CSS if you prefer.

## Installation

Simply copy the code snippet below into the PHP file where you want the notifications to appear. Make sure that the `$success` or `$err` variables are set before including the snippet.

## Usage

### Example

Below is an example of how to set up and use the toast notifications in your PHP project:

```php
<?php
// Example usage: set either a success or error message
$success = "Your action was successful!";
// Or for an error message:
// $err = "Something went wrong. Please try again.";
?>

<!-- Toast Notification -->
<?php if (isset($success)): ?>
    <div id="successToast" class="fixed top-4 right-4 p-4 bg-green-50 rounded-lg shadow-lg transition-opacity duration-500">
        <p class="text-green-600 text-sm"><?php echo $success; ?></p>
    </div>
    <script>
        setTimeout(() => {
            document.getElementById('successToast').style.opacity = '0';
            setTimeout(() => {
                document.getElementById('successToast').style.display = 'none';
            }, 500);
        }, 3000);
    </script>
<?php endif; ?>

<?php if (isset($err)): ?>
    <div id="errorToast" class="fixed top-4 right-4 p-4 bg-red-50 rounded-lg shadow-lg transition-opacity duration-500">
        <p class="text-red-600 text-sm"><?php echo $err; ?></p>
    </div>
    <script>
        setTimeout(() => {
            document.getElementById('errorToast').style.opacity = '0';
            setTimeout(() => {
                document.getElementById('errorToast').style.display = 'none';
            }, 500);
        }, 8000);
    </script>
<?php endif; ?>
```

#Customization
##Timeouts:

The success toast disappears after 3000 milliseconds (3 seconds).
The error toast disappears after 8000 milliseconds (8 seconds).
You can adjust these durations by modifying the delay values in the setTimeout functions.

##Styling:

The snippet uses Tailwind CSS classes (e.g., bg-green-50, text-green-600). If you're not using Tailwind, replace these with your custom CSS classes.
Positioning:

The notifications are positioned at the top-right of the viewport (fixed top-4 right-4). To change the position, modify these Tailwind classes or use your own CSS.
Contributing
Contributions, bug reports, and feature suggestions are welcome! Feel free to open an issue or submit a pull request if you have any improvements or ideas.

License
This project is licensed under the MIT License.
