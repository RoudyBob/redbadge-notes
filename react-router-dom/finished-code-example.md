# Finished Code Example

## index.tsx

```typescript
import React from "react";
import ReactDOM from "react-dom";
import "./index.css";
import App from "./App";
import reportWebVitals from "./reportWebVitals";
import "bootstrap/dist/css/bootstrap.min.css";
import { BrowserRouter } from "react-router-dom";

ReactDOM.render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>,
  document.getElementById("root")
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();

```

## app.tsx

```typescript
import React from "react";
import Contact from "./components/Contact.jsx";
import MainPage from "./components/MainPage";
import SiteBar from "./components/Navbar.jsx";
import Store from "./components/Store.jsx";
import { Route, Switch } from 'react-router-dom';

function App() {
  return (
    <div>
      <SiteBar />
      <Switch>
        <Route exact path="/contact" component={Contact} />
        <Route exact path="/store" component={Store} />
        {/* Another Way of Routing with Props */}
        <Route exact path="/alt"><MainPage title="This is a test" /></Route>
        <Route exact path="/" component={() => <MainPage title="This is a test" />}/>
      </Switch>
    </div>
  );
}

export default App;
```

## mainpage.tsx

```typescript
import React from "react";
import { Container, UncontrolledCarousel } from "reactstrap";


const items = [
  {
    src:
      "data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%22800%22%20height%3D%22400%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%20800%20400%22%20preserveAspectRatio%3D%22none%22%3E%3Cdefs%3E%3Cstyle%20type%3D%22text%2Fcss%22%3E%23holder_15ba800aa1d%20text%20%7B%20fill%3A%23555%3Bfont-weight%3Anormal%3Bfont-family%3AHelvetica%2C%20monospace%3Bfont-size%3A40pt%20%7D%20%3C%2Fstyle%3E%3C%2Fdefs%3E%3Cg%20id%3D%22holder_15ba800aa1d%22%3E%3Crect%20width%3D%22800%22%20height%3D%22400%22%20fill%3D%22%23777%22%3E%3C%2Frect%3E%3Cg%3E%3Ctext%20x%3D%22285.921875%22%20y%3D%22218.3%22%3EFirst%20slide%3C%2Ftext%3E%3C%2Fg%3E%3C%2Fg%3E%3C%2Fsvg%3E",
    altText: "Slide 1",
    caption: "Slide 1",
    header: "Slide 1 Header",
    key: "1",
  },
  {
    src:
      "data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%22800%22%20height%3D%22400%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%20800%20400%22%20preserveAspectRatio%3D%22none%22%3E%3Cdefs%3E%3Cstyle%20type%3D%22text%2Fcss%22%3E%23holder_15ba800aa20%20text%20%7B%20fill%3A%23444%3Bfont-weight%3Anormal%3Bfont-family%3AHelvetica%2C%20monospace%3Bfont-size%3A40pt%20%7D%20%3C%2Fstyle%3E%3C%2Fdefs%3E%3Cg%20id%3D%22holder_15ba800aa20%22%3E%3Crect%20width%3D%22800%22%20height%3D%22400%22%20fill%3D%22%23666%22%3E%3C%2Frect%3E%3Cg%3E%3Ctext%20x%3D%22247.3203125%22%20y%3D%22218.3%22%3ESecond%20slide%3C%2Ftext%3E%3C%2Fg%3E%3C%2Fg%3E%3C%2Fsvg%3E",
    altText: "Slide 2",
    caption: "Slide 2",
    header: "Slide 2 Header",
    key: "2",
  },
  {
    src:
      "data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%22800%22%20height%3D%22400%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%20800%20400%22%20preserveAspectRatio%3D%22none%22%3E%3Cdefs%3E%3Cstyle%20type%3D%22text%2Fcss%22%3E%23holder_15ba800aa21%20text%20%7B%20fill%3A%23333%3Bfont-weight%3Anormal%3Bfont-family%3AHelvetica%2C%20monospace%3Bfont-size%3A40pt%20%7D%20%3C%2Fstyle%3E%3C%2Fdefs%3E%3Cg%20id%3D%22holder_15ba800aa21%22%3E%3Crect%20width%3D%22800%22%20height%3D%22400%22%20fill%3D%22%23555%22%3E%3C%2Frect%3E%3Cg%3E%3Ctext%20x%3D%22277%22%20y%3D%22218.3%22%3EThird%20slide%3C%2Ftext%3E%3C%2Fg%3E%3C%2Fg%3E%3C%2Fsvg%3E",
    altText: "Slide 3",
    caption: "Slide 3",
    header: "Slide 3 Header",
    key: "3",
  },
];

interface MainPageProps {
  title: string,
}

const MainPage = (props: MainPageProps) => {
  return (
    <Container>
      <UncontrolledCarousel items={items} />
      <h2>This is my main MainPage</h2>
      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Assumenda
        optio, impedit, voluptates perspiciatis ipsum quisquam aspernatur,
        eveniet dolorum ducimus nulla esse nihil? Assumenda, tenetur placeat
        quis asperiores magni repudiandae quam?
      </p>
      <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quisquam,
        vitae eligendi autem magnam, blanditiis repudiandae cupiditate fuga
        quos, expedita nemo ab est obcaecati? Quia maiores quidem cumque quae!
        Vero, debitis.
      </p>
    </Container>
  );
};

export default MainPage;

```

## navbar.tsx

```typescript
import React, { useState } from "react";
import { Link } from 'react-router-dom';
import {
  Collapse,
  Navbar,
  NavbarToggler,
  NavbarBrand,
  Nav,
  NavItem,
  NavLink,
} from "reactstrap";

const SiteBar = (props) => {
  const [collapsed, setCollapsed] = useState(true);

  const toggleNavbar = () => setCollapsed(!collapsed);

  return (
    <div>
      <Navbar color="primary" dark>
        <Link to="/">
          <NavbarBrand className="me-auto" onClick={toggleNavbar}>Home</NavbarBrand>
        </Link>
        <NavbarToggler onClick={toggleNavbar} className="me-2" />
        <Collapse isOpen={!collapsed} navbar>
          <Nav navbar>
            <NavItem>
              <Link to="/contact" onClick={toggleNavbar}>
                <NavLink>Contact</NavLink>
              </Link>
            </NavItem>
            <NavItem>
              <Link to="/store" onClick={toggleNavbar}>
                <NavLink>Store</NavLink>
              </Link>
            </NavItem>
          </Nav>
        </Collapse>
      </Navbar>
    </div>
  );
};

export default SiteBar;

```



