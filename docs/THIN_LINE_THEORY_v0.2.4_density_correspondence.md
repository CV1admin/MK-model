# Thin Line Theory — Research Specification v0.2.4

**Status:** Research specification; not a validated physical theory  
**Repository:** CV1admin/MK-model  
**Branch:** docs/tlt-v0.2.4-density-correspondence  
**Scope:** Q7 physical correspondence between the original density-ratio variable and a candidate quantum observable.

## 1. Decision and scope

The original density-based TLT definition remains primary:

\[
x_\rho=\frac{\rho_E}{\rho_{E,\max}},\qquad
\chi_\rho=2x_\rho-1.
\]

The auxiliary quantum candidate remains distinct:

\[
x_Q=\operatorname{Tr}(\rho_4 X),\qquad
\chi_Q=2x_Q-1.
\]

No identity \(x_\rho=x_Q\) is assumed. Q7 is a blocking gate for interpreting quantum-sector calculations as predictions of the original TLT. Mathematical analysis of auxiliary models may continue, but must be labelled as such.

This document investigates Route A (derive a correspondence). Route B (explicitly revise the definition of TLT) remains a separate decision and is not adopted here.

## 2. Candidate physical meaning of the density

A possible relativistic starting point is the energy density measured by an observer with four-velocity \(u^\mu\):

\[
\rho_E(x)=T_{\mu\nu}(x)u^\mu u^\nu,
\]

where \(T_{\mu\nu}\) is the matter stress-energy tensor. This is a candidate interpretation only. It is not yet established that the original TLT symbol \(\rho_E\) means this quantity.

The following possibilities must not be conflated:

- local energy density;
- spatially coarse-grained energy density;
- energy density assigned to a specified field sector;
- vacuum-subtracted or renormalised energy density;
- a spectral or other model-specific density.

For a first controlled investigation, define a spatially smeared quantity on a spatial hypersurface \(\Sigma_t\):

\[
\rho_{E,L}(x)=
\int_{\Sigma_t}d^3y\,\sqrt{h(y)}\,
W_L(x,y)\rho_E(y),
\]

with normalised window function

\[
\int_{\Sigma_t}d^3y\,\sqrt{h(y)}\,W_L(x,y)=1.
\]

Here \(L\) denotes the characteristic coarse-graining scale. The quantum version requires a specified renormalised stress-energy operator and smearing prescription:

\[
\hat\rho_{E,L}(x)=
\int_{\Sigma_t}d^3y\,\sqrt{h(y)}\,
W_L(x,y)\hat T_{\mu\nu}(y)u^\mu u^\nu.
\]

This definition is a research candidate, not a completed identification. Renormalisation, observer choice, geometry, field content, and the smearing window must be specified in any physical application.

## 3. Candidate operator and existence conditions

If, on a specified restricted Hilbert-space sector,

1. \(\hat\rho_{E,L}\) is self-adjoint;
2. it is positive semidefinite;
3. its spectrum is bounded above by a finite, state-independent \(\rho_{E,\max}>0\);

then define

\[
X_L=\frac{\hat\rho_{E,L}}{\rho_{E,\max}}.
\]

It follows that \(0\leq X_L\leq\mathbb I\), and

\[
x_Q=\operatorname{Tr}(\rho_4X_L)
=\frac{\operatorname{Tr}(\rho_4\hat\rho_{E,L})}
{\rho_{E,\max}}.
\]

Under the additional identification

\[
\rho_E:=\operatorname{Tr}(\rho_4\hat\rho_{E,L}),
\]

and with the same fixed maximum used in the original ratio, one obtains \(x_\rho=x_Q\) within that restricted model.

These are sufficient conditions for the proposed construction, not claims that generic quantum field theory satisfies them. Renormalised local energy densities are not generally positive operators with a finite upper spectral bound. Many field Hamiltonians have unbounded spectra. Therefore \(X=\hat\rho_E/\rho_{E,\max}\) is not a valid universal bounded effect in unrestricted QFT.

A finite-dimensional truncation or a physically justified restricted sector may admit such an operator, but the truncation and its validity domain must be reported.

## 4. State-dependent normalisation obstruction

If the maximum depends on the state or environment,

\[
\rho_{E,\max}=\rho_{E,\max}(\rho_4),
\]

then

\[
x_\rho=
\frac{\operatorname{Tr}(\rho_4\hat\rho_{E,L})}
{\rho_{E,\max}(\rho_4)}
\]

is generally nonlinear in \(\rho_4\).

For any fixed operator \(X\), the map \(\rho_4\mapsto\operatorname{Tr}(\rho_4X)\) is linear. Consequently, a universal fixed linear observable cannot reproduce an arbitrary state-dependent normalisation over the full state space. Special restricted state families may still admit a correspondence, but that requires an explicit proof.

This obstruction does not establish that every state-dependent normalisation is impossible to represent by every conceivable nonlinear or state-dependent construction. It rules out the general fixed-operator representation under the stated assumptions.

## 5. Worked equality example: bounded two-level sector

Take a two-level Hilbert space \(\mathcal H=\operatorname{span}\{|0\rangle,|1\rangle\}\), with

\[
\hat H=E_0|1\rangle\langle1|,\qquad E_0>0,
\]

and a state

\[
\rho=p|1\rangle\langle1|+(1-p)|0\rangle\langle0|,
\qquad 0\leq p\leq1.
\]

Choose the fixed maximum \(E_{\max}=E_0\). Then

\[
\rho_E=\operatorname{Tr}(\rho\hat H)=pE_0,
\qquad x_\rho=p.
\]

With

\[
X=\frac{\hat H}{E_0}=|1\rangle\langle1|,
\]

we obtain

\[
x_Q=\operatorname{Tr}(\rho X)=p=x_\rho.
\]

This demonstrates equality in a finite-dimensional, bounded, fixed-normalisation model. It does not establish the same identification for the original TLT physical system.

## 6. Worked failure example: unbounded oscillator

For a harmonic oscillator,

\[
\hat H=\hbar\omega\left(\hat a^\dagger\hat a+\frac12\right),
\]

the energy eigenvalues are

\[
E_n=\hbar\omega\left(n+\frac12\right),
\qquad n=0,1,2,\ldots
\]

and are unbounded above. For any finite positive \(E_{\max}\), sufficiently large \(n\) gives

\[
\langle n|\hat H/E_{\max}|n\rangle>1.
\]

Thus \(X=\hat H/E_{\max}\) cannot satisfy \(0\leq X\leq\mathbb I\) on the full oscillator Hilbert space. This is a counterexample to the unrestricted bounded-operator construction, not to every possible restricted or nonlinear correspondence.

## 7. Dynamical preservation

For a closed system with unitary evolution generated by \(H\), and a time-independent observable \(X\),

\[
\frac{d}{dt}\langle X\rangle
=\frac{i}{\hbar}\operatorname{Tr}(\rho[H,X]).
\]

If \([H,X]=0\), then \(x_Q\) is conserved. If the commutator is nonzero, the observable generally evolves. Equality at one instant therefore does not prove equality at later times.

For a subsystem coupled to an extra sector, the correct starting point is the total state and total Hamiltonian. With \(X\) acting on the observable sector,

\[
\frac{d}{dt}\langle X\otimes\mathbb I_E\rangle
=\frac{i}{\hbar}
\operatorname{Tr}\!\left(\rho_D[H_D,X\otimes\mathbb I_E]\right).
\]

An interaction can make this commutator nonzero. The reduced subsystem evolution may then be non-unitary, even if the total evolution is unitary. A correspondence must be checked under the actual coupled dynamics, not inferred from a decoupled or fixed-time example.

## 8. Q7 sub-gates

| Gate | Requirement | Status |
|---|---|---|
| Q7.1 | Recover the original physical definition of \(\rho_E\) and the procedure fixing \(\rho_{E,\max}\) | Open |
| Q7.2 | Establish self-adjointness, positivity, boundedness, renormalisation and operator domain | Conditional construction only |
| Q7.3 | Prove equality on a stated state space; identify counterexamples and limits | Restricted example and unrestricted counterexample supplied |
| Q7.4 | Test preservation under free and coupled dynamics | General criterion supplied; TLT-specific test open |

## 9. Relation to the wider TLT programme

- **Primary TLT:** retain the original density-ratio definition until its foundational source defines both numerator and maximum.
- **Quantum auxiliary formulation:** retain \(x_Q\) as a separate observable until Q7 is resolved.
- **MK extension:** an optional coupled-sector hypothesis. Its Hilbert-space factorisation and coupling must be justified for the selected physical model.
- **Nonlinear closure (Q8):** Gaussian/Hartree closure is an approximation, not an identity. Interacting moment hierarchies require a stated closure or controlled expansion.
- **Consciousness research (TLT-C):** independent exploratory branch; it is not evidence for the physical correspondence.
- **VIREÁX:** independent verification and provenance layer; it does not substitute for physical derivation.

## 10. Acceptance criteria for closing Q7

Q7 cannot be closed until a versioned derivation provides:

1. the exact original definitions of \(\rho_E\) and \(\rho_{E,\max}\);
2. units, dimensions, observer/frame, spatial or temporal coarse-graining, and renormalisation prescription where applicable;
3. the operator or alternative mathematical representation and its domain;
4. the state space and conditions under which equality is claimed;
5. at least one equality example and deliberate counterexample analysis;
6. preservation or failure under free and coupled dynamics;
7. a recoverable link from the derivation to an independently testable physical prediction.

## 11. Current conclusion

The correspondence is demonstrated only in a restricted two-level example. The unrestricted oscillator example shows why a finite, state-independent maximum cannot be assumed for general quantum systems. The physical meaning of the original TLT density and its maximum remains unresolved.

**No physical TLT prediction, cosmological attractor claim, or universal quantum correspondence follows from this document.** This specification records a mathematical research programme and its current limitations; it is not a claim of experimental validation.

---

**Change control:** This document does not redefine the original TLT variables, replace the primary theory, or authorise changes to other repositories or systems.
