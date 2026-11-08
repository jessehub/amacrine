
retinal-anomaly-engine (RAE)

A lightweight, zero-backend edge detection engine for software logs, operating entirely as an outgoing log transformer.
RAE strips out the need for high-compute time-series storage, analytical databases, or central anomaly detection frameworks. Instead, it embeds directly inside your active logging path as a stateless, self-cleaning filter that suppresses background system noise and amplifies critical architectural faults before they ever leave the host.

The Core Concept

RAE processes inbound logs through a fast, in-memory matrix inspired by biological peripheral vision, acting as a competitive triage filter:
• Spatial Funneling: Raw log patterns are instantly aggregated into local execution contexts (such as pod groups or cluster namespaces). Localized, low-frequency blips are absorbed seamlessly within the baseline capacity.
• Logarithmic Decay Cache: Firing event patterns write immediate intensity scores to an in-memory transactional cache. These weights decay over time on a logarithmic curve, preserving critical data directly after an incident while flatlining long-standing steady states into background noise to completely erase alert fatigue.
• Competitive Lateral Inhibition: Before a high-intensity log triggers an outbound alert endpoint, it faces a cross-cache suppression check from its logical "neighbors" (e.g., sister instances across a shared load balancer).
	• Coordinated Global Noise: If a core database drops, all instances spike with identical log signatures at the exact same moment. Because all neighbors fire equally, they mutually inhibit each other to zero—suppressing massive alert storms.
	• True Outlier Edges: If a single microservice instance begins throwing error strings while its neighbor cluster remains quiet, there is no lateral inhibition to damp the signal. The outlier cuts through the silence instantly, passing through the transformer as a razor-sharp anomaly edge.

Roadmap (TODO)

• Core Engine: Build the lock-free, concurrent log-decay matrix map.
• Inhibition Groups: Implement infrastructure neighbor configuration schemas.
• Runtime Fuzzy Clustering: Design the automated runtime string-matching parser using a user-definable threshold parameter to bucket unexpected log variations without explicit rules.
