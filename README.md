Vector-Shift Pipeline Editor

A playful, modular React-based pipeline editor for building and visualizing node-based workflows. Designed with pastel themes, draggable components, and a clean React Flow canvas.

 Features

Drag-and-drop node creation from a custom toolbar

Custom node types: Input, LLM, Output, and Text

Smooth edge connections with animated arrows

Submit pipeline to backend API for DAG validation

Modular Zustand store for managing nodes and edges

React Flow integration with background grid, minimap, and controls

 Folder Structure

frontend/
├── src/
│   ├── nodes/               # Custom node components
│   │   ├── InputNode.js
│   │   ├── LLMNode.js
│   │   ├── OutputNode.js
│   │   └── TextNode.js
│   ├── toolbar.js           # PipelineToolbar with draggable buttons
│   ├── draggableNode.js     # DraggableNode component
│   ├── ui.js                # PipelineUI canvas with React Flow
│   ├── store.js             # Zustand store for node/edge state
│   ├── submit.js            # SubmitButton component
│   └── App.js               # Main app layout

🧩 Node Types

Each node is styled with pastel colors and Comic Sans font:

InputNode: Accepts name and type (Text/File)

LLMNode: Accepts prompt text

OutputNode: Accepts name and output type

TextNode: Accepts a templated text string

🛠 Setup & Run

# Install dependencies
npm install

# Start development server
npm start

If prompted to use another port, type yes.

📡 Backend Integration

The SubmitButton sends the current pipeline to:

POST http://127.0.0.1:8000/pipelines/parse

Payload:

{
  "nodes": [...],
  "edges": [...]
}

Response:

{
  "num_nodes": 4,
  "num_edges": 3,
  "is_dag": true
}

🧠 State Management

Zustand store (store.js) handles:

Node ID generation

Node/edge updates

Edge connections with arrow markers

Field updates for each node

 ESLint Tips

Ensure all imports match actual file paths (e.g. ./nodes/InputNode)

Remove unused imports like useNodesState or useEdgesState

Include all dependencies in useCallback hooks

 Customization Ideas

Add new node types (e.g. API call, conditional logic)

Add theme toggle or dark mode

Visualize pipeline execution order

Export pipeline as JSON or image

 Design Notes

Font: Comic Sans MS

Colors: Pastel pinks, soft gradients

Borders: Dashed pink (#ff69b4)

Shadows: Light and playful
