import { useEffect, useState } from "react";

export default function App() {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState("");

  useEffect(() => {
    const fetchUsers = async () => {
      try {
        setLoading(true);

        const response = await fetch(
          "https://jsonplaceholder.typicode.com/users"
        );

        if (!response.ok) {
          throw new Error("Failed to fetch users.");
        }

        const data = await response.json();

        // First 5 users only
        setUsers(data.slice(0, 5));
      } catch (err) {
        setError("Failed to fetch users.");
      } finally {
        setLoading(false);
      }
    };

    fetchUsers();
  }, []);

  return (
    <div className="min-h-screen bg-lime-950 relative overflow-hidden py-10">
      
      {/* Right Curved Shape */}
      <div className="absolute top-0 right-0 w-[60%] h-full bg-teal-900 rounded-l-full"></div>

      {/* Content */}
      <div className="relative z-10 flex flex-col items-center">
        
        {/* Title */}
        <h1 className="text-6xl font-extrabold text-violet-200 text-center leading-tight">
          Simple User <br /> Directory
        </h1>

        {/* Subtitle */}
        <p className="text-2xl text-violet-100 mt-4 mb-10">
          Yeasha Mei P. Diño
        </p>

        {/* Loading */}
        {loading && (
          <p className="text-2xl text-violet-100">
            Loading users...
          </p>
        )}

        {/* Error */}
        {error && (
          <p className="text-2xl text-red-400">
            {error}
          </p>
        )}

        {/* User Cards */}
        <div className="flex flex-col gap-12 w-full items-center">
          {users.map((user) => (
            <div
              key={user.id}
              className="w-[75%] bg-violet-300 border-8 border-fuchsia-500 p-8 shadow-2xl"
            >
              {/* Name */}
              <h2 className="text-3xl font-bold text-violet-950 mb-5">
                {user.name}
              </h2>

              {/* Email */}
              <p className="text-xl text-violet-900 mb-3">
                <span className="font-semibold">Email:</span> {user.email}
              </p>

              {/* Company */}
              <p className="text-xl text-violet-900">
                <span className="font-semibold">Company:</span>{" "}
                {user.company.name}
              </p>
            </div>
          ))}
        </div>
      </div>
    </div>
  );
}
