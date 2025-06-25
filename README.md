
# 🚗 Smart Parking System with Analytics

A scalable and intelligent Java-based parking management system designed to handle real-time vehicle entry/exit, VIP prioritization, dynamic slot allocation, and analytics reporting.

---

## 📌 Features

- ✅ Real-time vehicle check-in and check-out
- ⭐ VIP prioritization using Max-Heap
- 🔄 FIFO regular slot management with Circular Queue
- 📋 Chronological entry/exit logging with LinkedList
- 📊 On-demand analytics generation
- ⚡ Fast, memory-efficient, and highly scalable
- 🧩 Modular and extendable architecture

---

## 🧠 Data Structures Used

| Data Structure     | Purpose                                        | Implementation                  |
|--------------------|------------------------------------------------|----------------------------------|
| Circular Queue      | Regular slot allocation (FIFO)                | `ArrayDeque<Slot>`              |
| HashMap             | Active vehicle registry                       | `HashMap<String, Vehicle>`      |
| LinkedList          | Entry/exit log for analytics                  | `LinkedList<LogEntry>`          |
| Max-Heap (Priority Queue) | VIP slot management                        | `PriorityQueue<Slot>` with Comparator |

---

## 📁 Project Structure

```
SmartParkingSystem/
├── src/
│   ├── Slot.java
│   ├── Vehicle.java
│   ├── LogEntry.java
│   ├── EntryExitLog.java
│   ├── AnalyticsEngine.java
│   ├── ParkingManager.java
│   └── SmartParkingSystem.java
├── test/
│   └── SystemTests.java
├── README.md
└── LICENSE
```

---

## ⚙️ How It Works

### ✅ Vehicle Entry

```java
parkingManager.vehicleEntry("VIP-001", true);
```

- VIP: Allocated from `Max-Heap`
- Regular: Allocated from `CircularQueue`
- Vehicle stored in `HashMap`
- Log entry created

### 🚪 Vehicle Exit

```java
parkingManager.vehicleExit("VIP-001");
```

- Slot released and returned to proper structure
- Exit time updated in log
- Vehicle removed from registry

### 📊 Analytics Report

```java
analyticsEngine.generateReport();
```

- Total vehicles
- Peak hour
- Average stay duration

---

## 📈 Performance Benchmarks

| Operation               | Avg Time | Time Complexity |
|------------------------|----------|-----------------|
| Regular Slot Allocation | <1ms     | O(1)            |
| VIP Slot Allocation     | <2ms     | O(log n)        |
| Vehicle Lookup          | <0.5ms   | O(1)            |
| Analytics Generation    | <100ms   | O(n)            |

---

## 🧪 Testing

Sample Test Scenarios:

| Test Case                     | Input                   | Expected Output         | Result |
|------------------------------|--------------------------|--------------------------|--------|
| VIP Entry                    | VIP-0001, true           | VIP Slot V1 assigned     | ✅     |
| Regular Entry                | REG-0002, false          | Regular Slot R12 assigned| ✅     |
| Vehicle Exit                 | REG-0002                 | Slot R12 freed           | ✅     |
| No Available Slots           | VEH-1001                 | No available slot        | ✅     |
| Analytics Generation         | Logs                     | Peak hour, avg stay      | ✅     |

---

## 🧠 Sample Analytics Output

```
Analytics Report:
---------------------------
Peak Hour      : 10:00
Average Stay   : 21.25 minutes
Total Vehicles : 4
```

---

## 🌍 Real-World Applications

- 🏢 Shopping Malls & Corporate Parking
- 🛫 Airports & Transportation Hubs
- 🏟️ Event Venues
- 🚦 Smart City Infrastructure
- 🏬 Commercial Parking Facilities

---

## 🚀 Future Enhancements

### Immediate Features
- 💳 Payment Gateway Integration
- 📱 Mobile App for Slot Booking
- 📊 Web Dashboard for Admin
- 🔔 SMS/Email Notifications

### Advanced Features
- 🎥 License Plate Recognition (LPR)
- 💸 Dynamic Pricing (Peak hours)
- 🤖 Predictive Analytics (Machine Learning)
- 🌐 IoT-based Slot Occupancy Detection
- 🗺️ Multi-location Management

---

## 🧱 Architecture Overview

```
Presentation Layer (CUI)
        ↓
Business Logic Layer (ParkingManager)
        ↓
Data Layer (HashMap, Queue, Heap, LinkedList)
        ↓
Analytics Layer (AnalyticsEngine)
```

- 🧵 Single-threaded design (easy to extend with synchronization)
- 🧠 In-memory data for speed
- 📦 Ready for persistence layer integration

---

## 📜 License

This project is licensed under the [MIT License](https://choosealicense.com/licenses/mit/).

---

## 🤝 Contributing

Pull requests are welcome!

- Open an issue for major changes.
- Ensure all test cases pass.
- Follow Java naming and formatting conventions.

---

## 👥 Authors

Developed by **Faizan** and Team  
🎓 Final Year Project | Java | 2025
