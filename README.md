# react
assignment3
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Drill Down Props Example</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f4f4f4;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      background-color: #007bff; /* Blue color */
      color: white;
      border: none;
      border-radius: 5px;
    }
    button:hover {
      background-color: #0056b3; /* Darker blue on hover */
    }
    .container {
      background-color: #ffffff;
      border-radius: 10px;
      padding: 20px;
      margin: 0 auto;
      max-width: 400px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    h1 {
      color: #333333;
    }
    h2 {
      color: #007bff;
    }
    h3 {
      color: #4CAF50; /* Green color */
    }
    p {
      color: #666666;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Drill Down Props Example</h1>
    <div id="root"></div>
  </div>

  <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
  <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
  <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>

  <script type="text/babel">
    const { useState } = React;

    const ParentComponent = ({ data }) => {
      return (
        <div>
          <h2>Parent Component</h2>
          <p>Parent Data: {data}</p>
          <ChildComponent data={data} />
        </div>
      );
    }

    const ChildComponent = ({ data }) => {
      return (
        <div>
          <h3>Child Component</h3>
          <p>Received data from parent: {data}</p>
        </div>
      );
    }

    const App = () => {
      const [parentData, setParentData] = useState("Data from parent");

      return (
        <div>
          <ParentComponent data={parentData} />
          <button onClick={() => setParentData("Updated data from parent")}>
            Update Parent Data
          </button>
        </div>
      );
    }

    ReactDOM.render(<App />, document.getElementById('root'));
  </script>
</body>
</html>
