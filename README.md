# Technical Assessment: Query Optimization & Efficiency

## Objective
To demonstrate high-performance backend logic and memory management using Pythonic standards.

## import time
from functools import lru_cache

# Senior Engineer Approach: Using Memoization to optimize query performance
@lru_cache(maxsize=100)
def get_complex_data(query_id):
    # Simulating a heavy database query
    time.sleep(2) 
    return {"id": query_id, "data": "Optimized Result", "status": "Success"}

def process_request(query_id):
    start_time = time.time()
    result = get_complex_data(query_id)
    execution_time = time.time() - start_time
    print(f"Query ID {query_id} processed in {execution_time:.4f} seconds.")
    return result, execution_time

if __name__ == "__main__":
    print("Fetching data for ID 1 (First time)...")
    process_request(1)
    print("Fetching data for ID 1 (Second time - Cached)...")
    process_request(1)
j
