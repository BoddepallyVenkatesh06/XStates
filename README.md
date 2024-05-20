# XStates

XStates is a state management library designed to simplify the management of complex states in your web application. It provides an easy-to-use API and powerful features that can be seamlessly integrated into any React application.

## Table of Contents 📚

- [Introduction🚀](#introduction)
- [Features🛠️](#features)
- [Screenshot📷](#screenshot)
- [Getting Started🎯](#getting-started)
- [Prerequisites📋](#prerequisites)
- [Installation⚙️](#installation)
- [Usage📈](#usage)
- [API Documentation🔌](#api-documentation)
- [Contributing❤️](#contributing)
- [License📝](#license)

## Introduction🚀

XStates simplifies state management in your React application by providing a robust and flexible library that handles complex state logic efficiently. It ensures your application state is predictable and easy to debug.

## Features🛠️

- Easy-to-use API
- Support for complex state transitions
- Middleware support for side effects
- DevTools integration for easy debugging
- TypeScript support for type safety

## Screenshot📷

![XStates Module](https://github.com/BoddepallyVenkatesh06/XStates/blob/main/Screenshot_XStates.png)

## Getting Started🎯

### Prerequisites📋

Before you begin, ensure you have the following installed on your system:
- Node.js
- npm (Node Package Manager)
- React (for the application where XStates will be integrated)

### Installation⚙️

1. Install XStates via npm:

```bash
npm install xstates
```

## Usage📈

### Basic Setup

1. Create a state machine configuration:

```javascript
import { createMachine } from 'xstates';

const toggleMachine = createMachine({
  id: 'toggle',
  initial: 'inactive',
  states: {
    inactive: {
      on: { TOGGLE: 'active' }
    },
    active: {
      on: { TOGGLE: 'inactive' }
    }
  }
});
```

2. Use the machine in your React component:

```javascript
import React from 'react';
import { useMachine } from 'xstates/react';
import { toggleMachine } from './path-to-your-machine';

const ToggleComponent = () => {
  const [state, send] = useMachine(toggleMachine);

  return (
    <button onClick={() => send('TOGGLE')}>
      {state.matches('inactive') ? 'Activate' : 'Deactivate'}
    </button>
  );
};

export default ToggleComponent;
```

## API Documentation🔌

### `createMachine`

Creates a new state machine.

**Parameters:**
- `config` (object): The configuration object for the state machine.

**Returns:**
- A state machine instance.

### `useMachine`

A React hook to use a state machine in a component.

**Parameters:**
- `machine` (object): The state machine instance.

**Returns:**
- An array with the current state and a send function.

## Contributing❤️

Contributions are welcome! If you'd like to contribute to XStates, please follow these steps:

1. Fork the project.
2. Create a new branch: `git checkout -b feature-name`.
3. Commit your changes: `git commit -m 'Add some feature'`.
4. Push to the branch: `git push origin feature-name`.
5. Submit a pull request.

## License📝

```
MIT License

Copyright (c) 2024 Venky Kumar

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
