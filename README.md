# Flick-flow
A reactive app for watching movies 
// 📁 src/main.jsx import React from 'react'; import ReactDOM from 'react-dom/client'; import App from './App.jsx'; import './index.css';

ReactDOM.createRoot(document.getElementById('root')).render( <React.StrictMode> <App /> </React.StrictMode> );

// 📁 src/App.jsx import { BrowserRouter as Router, Routes, Route } from 'react-router-dom'; import Navbar from './components/Navbar'; import Home from './pages/Home'; import Movies from './pages/Movies'; import TVShows from './pages/TVShows'; import MyList from './pages/MyList';

function App() { return ( <Router> <div className="bg-black min-h-screen text-white"> <Navbar /> <Routes> <Route path="/" element={<Home />} /> <Route path="/movies" element={<Movies />} /> <Route path="/tv-shows" element={<TVShows />} /> <Route path="/my-list" element={<MyList />} /> </Routes> </div> </Router> ); }

export default App;

// 📁 src/components/Navbar.jsx import { Link } from 'react-router-dom';

export default function Navbar() { return ( <nav className="p-4 bg-gray-900 flex justify-between items-center"> <h1 className="text-2xl font-bold">🎬 FlickFlow</h1> <div className="space-x-4"> <Link to="/" className="hover:text-red-500">Home</Link> <Link to="/movies" className="hover:text-red-500">Movies</Link> <Link to="/tv-shows" className="hover:text-red-500">TV Shows</Link> <Link to="/my-list" className="hover:text-red-500">My List</Link> </div> </nav> ); }

// 📁 src/pages/Home.jsx import MovieCard from '../components/MovieCard'; import movies from '../data/movies';

export default function Home() { return ( <div className="p-4"> <h2 className="text-xl mb-4">Featured</h2> <div className="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4"> {movies.slice(0, 4).map(movie => ( <MovieCard key={movie.id} movie={movie} /> ))} </div> </div> ); }

// 📁 src/pages/Movies.jsx import MovieCard from '../components/MovieCard'; import movies from '../data/movies';

export default function Movies() { return ( <div className="p-4"> <h2 className="text-xl mb-4">All Movies</h2> <div className="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4"> {movies.map(movie => ( <MovieCard key={movie.id} movie={movie} /> ))} </div> </div> ); }

// 📁 src/pages/TVShows.jsx export default function TVShows() { return ( <div className="p-4"> <h2 className="text-xl mb-4">TV Shows (Coming Soon)</h2> <p className="text-gray-400">Stay tuned for TV series and exclusive shows.</p>

