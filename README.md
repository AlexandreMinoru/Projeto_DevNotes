
# Dev Notes

Dev Notes is a simple web application for managing and organizing your notes. It allows you to add, edit, delete, and export notes in a convenient way. The application is built using HTML, CSS, and JavaScript.

## Table of Contents

- [Elements](#elements)
- [Functions](#functions)
- [Local Storage](#local-storage)
- [Events](#events)
- [Initialization](#initialization)

## Elements

### `notesContainer`

```javascript
const notesContainer = document.querySelector("#notesContainer");
```

Container element for displaying notes.

### `noteInput`
```javascript
const noteInput = document.querySelector("#noteContent");
```

Input element for adding new notes.

### `addBtn`
```javascript
const addBtn = document.querySelector(".addNote");
```

Button element to add a new note.

### `searcInput`
```javascript
const searcInput = document.querySelector("#searchInput");
```

Input element for searching notes.

### `exportBtn`
```javascript
const exportBtn = document.querySelector("#exportNotes");
```

Button element to export notes to a CSV file.

## Functions
`showNotes()`
Displays all notes in the notesContainer.

`addNote()`
Adds a new note to the notesContainer and updates the local storage.

`generateId()`
Generates a random ID for a new note.

`createNote(id, content, fixed)`
Creates a new note element with specified ID, content, and fixed status.

`editNote(id, content)`
Edits the content of a note with the specified ID.

`toggleFixNotes(id)`
Toggles the fixed status of a note with the specified ID.

`removeNote(id, element)`
Removes a note with the specified ID and its corresponding HTML element.

`duplicateNote(id)`
Duplicates a note with the specified ID, creating a new note.

`cleanNotes()`
Clears all notes from the notesContainer.

`exportData()`
Exports notes data to a CSV file.

`getNotes()`
Retrieves notes from local storage, ordered by fixed status.

`saveNotes(notes)`
Saves notes to local storage.

`searchNotes(search)`
Searches notes based on the provided search term.

## Local Storage
`getNotes()`
```javascript
function getNotes() {
    const notes = JSON.parse(localStorage.getItem("notes") || "[]");
    const orderedNotes = notes.sort((a, b) => a.fixed > b.fixed ? -1 : 1);
    return orderedNotes;
}
```

Retrieves notes from local storage, ordered by fixed status.

`saveNotes(notes)`
```javascript
function saveNotes(notes) {
    localStorage.setItem("notes", JSON.stringify(notes));
}
```

Saves notes to local storage.

## Events
`addBtn` click event: Adds a new note.

`noteInput` keydown event: Adds a new note on pressing Enter.

`searcInput` keyup event: Searches notes based on input.

`exportBtn` click event: Exports notes to a CSV file.

## Initialization

Initializes the application by showing existing notes.
