# DeltaTable: Consistent Reads and Transactional Concurrency Control

This repo continues our step-by-step construction of a Delta Lake-inspired table format. In this phase, we focus on **reading data consistently** from a versioned transaction log and **handling concurrent writes** using optimistic transactions.

---

## 🎯 Objectives

- Enable **snapshot-based reads** from a versioned transaction log.
- Implement **optimistic concurrency control** to ensure safe multi-writer commits.
- Explore how failures and retries are handled safely in a transactional log-based system.

---

## 📖 Consistent Reads via Versioned Logs

### 🧠 Concept

Each transaction writes a versioned log file (e.g., `00000000000000000001.json`). These logs contain a list of **Actions** such as:

## 🔄 Task: Write a Test for Concurrent Transactions

Now that you've implemented transactional commits with concurrency control, it's time to **test the system under concurrent access**.

This task helps you verify that your `DeltaTable` correctly detects and handles conflicting writes using versioned logs.

---

### 🧪 Goal

Simulate multiple transactions running concurrently and attempting to commit changes. Ensure that:

- Only one transaction can successfully commit a given version.
- Other transactions either retry or fail with a conflict.
- The final state (i.e., snapshot) is consistent and includes only successfully committed data.

---

