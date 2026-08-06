# Hierarchy

1. Resolve the host's instruction root, traversal boundary, recognized filenames, and precedence.
2. Read the effective chain from root to target; ignore shadowed files and handle separate boundaries independently.
3. Put each rule at the highest directory where it stays true. Keep deeper files to local additions or narrow, explicit overrides.
4. Create a nested file only for local mandatory rules or small essential context that code and configuration cannot explain; link larger context and state the file's scope.
5. Check reachability, parent-child conflicts, and duplication.
