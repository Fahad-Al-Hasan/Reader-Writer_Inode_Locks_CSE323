
# Project Proposal
## Reader-Writer Inode Locks in xv6

**Course:** CSE323 - Operating Systems  
**University:** North South University  
**Project Type:** Operating System Kernel Modification  
**Base Operating System:** xv6  
**Programming Language:** C  
**Proposal Status:** Draft  

---

## 1. Group Information

| Name | Student ID | Email |
|---|---|---|
| Fahad Al Hasan | 2221317042 | fahad.hasan3@northsouth.edu |
| Nadira Halim Himla | 2221920642 | nadira.halim@northsouth.edu |
| Jannatul Ferdous Joty | 1813660642 | jannatul.ferdous.181@northsouth.edu |
| Aisha Nourunnisa Naziha | 2411799642 | aisha.naziha.241@northsouth.edu |

---

## 2. Project Overview

### 2.1 Project Description

[Provide a brief overview of the project, its purpose,
and the proposed modification to xv6.]

### 2.2 Motivation

[Explain why improving inode synchronization is an
interesting and important operating systems problem.]

---

## 3. Problem Statement

[Describe the limitations of the existing xv6 inode
locking mechanism.]

[Explain how exclusive inode locking affects
concurrent read operations.]

[Discuss the challenge of supporting multiple readers
without compromising data consistency or starving writers.]

---

## 4. Project Objectives

### 4.1 Primary Objectives

- Allow multiple readers to hold a shared inode lock.
- Ensure writers have exclusive access to an inode.
- Prevent writer starvation.
- Preserve filesystem correctness and consistency.

### 4.2 Additional Objectives

- [Specify additional objectives.]
- [Describe potential performance improvements.]
- [Identify any measurable synchronization goals.]

---

## 5. Background and Technical Concepts

### 5.1 Inodes in xv6

[Explain the role of inodes in the xv6 filesystem.]

### 5.2 Existing Inode Locking Mechanism

[Describe the current inode locking implementation
and relevant kernel functions.]

### 5.3 Reader-Writer Locks

[Explain shared reader access and exclusive writer access.]

### 5.4 Writer Starvation

[Explain how writer starvation can occur and why
the proposed implementation must prevent it.]

---

## 6. Proposed Solution

### 6.1 Design Overview

[Present the general architecture of the proposed
reader-writer inode locking mechanism.]

### 6.2 Reader Locking Mechanism

[Explain how concurrent readers will acquire and
release shared inode locks.]

### 6.3 Writer Locking Mechanism

[Explain how writers will acquire exclusive access
and release inode locks.]

### 6.4 Fairness and Starvation Prevention

[Describe the proposed fairness policy.]

[Explain how the design will ensure that writers
eventually acquire the lock.]

### 6.5 Synchronization and Correctness

[Explain how race conditions will be prevented.]

[Describe how mutual exclusion, shared access,
and safe lock transitions will be maintained.]

---

## 7. Implementation Plan

### 7.1 Development Environment

- Operating System: [Specify development environment]
- xv6 Version: [Specify xv6 version]
- Programming Language: C
- Emulator: QEMU
- Version Control: Git and GitHub

### 7.2 Relevant Kernel Components

[Identify the files, functions, and structures
that require modification.]

### 7.3 Implementation Steps

**Phase 1: Analysis**
- Study existing inode locking.
- Identify read and write operations.
- Determine synchronization requirements.

**Phase 2: Design**
- Design the reader-writer lock structure.
- Select a starvation-prevention policy.
- Identify required kernel changes.

**Phase 3: Implementation**
- Implement reader-writer synchronization.
- Integrate the mechanism into inode operations.
- Handle concurrency and lock transitions.

**Phase 4: Testing**
- Develop concurrency tests.
- Test writer starvation prevention.
- Verify filesystem correctness.

**Phase 5: Evaluation and Documentation**
- Measure performance.
- Compare results against baseline xv6.
- Document findings and limitations.

---

## 8. Testing and Evaluation

### 8.1 Correctness Testing

[Explain how concurrent operations will be tested
for race conditions and filesystem consistency.]

### 8.2 Concurrent Reader Testing

[Describe tests involving multiple simultaneous readers.]

### 8.3 Writer Starvation Testing

[Describe tests that verify waiting writers
eventually acquire the lock.]

### 8.4 Performance Evaluation

[Explain how the original and modified inode
locking mechanisms will be compared.]

**Proposed Evaluation Metrics:**

- Concurrent reader throughput
- Writer waiting time
- Overall filesystem operation throughput
- Lock acquisition latency
- Correctness under concurrent workloads

---

## 9. Expected Outcomes

[Describe the expected behavior of the modified
inode locking mechanism.]

[Explain the anticipated concurrency improvements.]

[Discuss how writer starvation prevention
will be demonstrated.]

---

## 10. Challenges and Limitations

### 10.1 Anticipated Challenges

- [Synchronization complexity]
- [Potential deadlocks]
- [Writer fairness]
- [Kernel integration challenges]

### 10.2 Project Limitations

[Describe the intended scope and any functionality
that will not be addressed.]

---

## 11. Task Distribution

| Group Member | Assigned Responsibilities | Status |
|---|---|---|
| Fahad Al Hasan | [To be assigned] | Not Started |
| Nadira Halim Himla | [To be assigned] | Not Started |
| Jannatul Ferdous Joty | [To be assigned] | Not Started |
| Aisha Nourunnisa Naziha | [To be assigned] | Not Started |

---

## 12. Project Timeline

| Phase | Tasks | Expected Completion |
|---|---|---|
| Phase 1 | Research and analysis | [Date] |
| Phase 2 | Design and planning | [Date] |
| Phase 3 | Implementation | [Date] |
| Phase 4 | Testing and debugging | [Date] |
| Phase 5 | Evaluation and documentation | [Date] |

---

## 13. References

1. [xv6: A Simple, Unix-like Teaching Operating System](https://pdos.csail.mit.edu/6.1810/2025/xv6.html)
2. [xv6 Source Code](https://github.com/mit-pdos/xv6-riscv)
3. [Add additional relevant papers or resources.]

---

## 14. Proposal Status

**Current Status:** Draft

**Last Updated:** [YYYY-MM-DD]

**Reviewed By:** [Names]

**Faculty Approval:** Pending
