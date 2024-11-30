import React, { useState } from "react";

const KanbanBoard = () => {
  const [tasks, setTasks] = useState({
    todo: [
      { id: "CAM-5", title: "Add Multi-Language Support", type: "Feature Request" },
      { id: "CAM-8", title: "Create Onboarding Tutorial for New Users", type: "Feature Request" },
      { id: "CAM-2", title: "Implement Email Notification System", type: "Feature Request" },
      { id: "CAM-1", title: "Update User Profile Page UI", type: "Feature Request" },
    ],
    inProgress: [
      { id: "CAM-3", title: "Optimize Database Queries for Performance", type: "Feature Request" },
    ],
    done: [
      { id: "CAM-6", title: "Enhance Search Functionality", type: "Feature Request" },
      { id: "CAM-7", title: "Integrate Third-Party Payment Gateway", type: "Feature Request" },
      { id: "CAM-11", title: "Conduct Security Vulnerability Assessment", type: "Feature Request" },
      { id: "CAM-10", title: "Upgrade Server Infrastructure", type: "Feature Request" },
      { id: "CAM-9", title: "Implement Role-Based Access Control (RBAC)", type: "Feature Request" },
    ],
    canceled: [],
  });

  return (
    <div style={{ display: "flex", gap: "1rem", padding: "1rem" }}>
      {Object.entries(tasks).map(([status, items]) => (
        <div key={status} style={{ flex: 1, border: "1px solid #ddd", borderRadius: "4px" }}>
          <h3 style={{ textAlign: "center", background: "#f5f5f5", margin: 0, padding: "0.5rem" }}>
            {status.charAt(0).toUpperCase() + status.slice(1)} ({items.length})
          </h3>
          <div style={{ padding: "0.5rem" }}>
            {items.map((task) => (
              <div
                key={task.id}
                style={{
                  border: "1px solid #ddd",
                  borderRadius: "4px",
                  padding: "0.5rem",
                  marginBottom: "0.5rem",
                  background: "#fff",
                }}
              >
                <strong>{task.id}</strong>: {task.title}
                <div style={{ fontSize: "0.85rem", color: "#888" }}>{task.type}</div>
              </div>
            ))}
          </div>
        </div>
      ))}
    </div>
  );
};

export default KanbanBoard;
